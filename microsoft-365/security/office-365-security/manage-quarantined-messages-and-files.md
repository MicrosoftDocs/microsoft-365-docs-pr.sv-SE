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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur administratörer kan hantera meddelanden och filer i karantän för användare i Office 365.
ms.openlocfilehash: e69887b54b3e892775c16fa3e306da3b17ab7db3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036179"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="39307-103">Hantera meddelanden och filer i karantän som administratör</span><span class="sxs-lookup"><span data-stu-id="39307-103">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="39307-104">Karantänen lagrar potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="39307-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="39307-105">Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="39307-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="39307-106">Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="39307-106">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="39307-107">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="39307-107">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="39307-108">Administratörer kan också rapportera falska positiva identifieringar till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39307-108">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="39307-109">Administratörer i organisationer med Office 365 Advance Threat Protection (ATP) kan också visa, hämta och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39307-109">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="39307-110">Du kan visa och hantera meddelanden i karantän i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="39307-110">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39307-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="39307-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39307-112">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="39307-112">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="39307-113">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="39307-113">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="39307-114">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="39307-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="39307-115">Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="39307-115">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="39307-116">Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantänrollen** i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="39307-116">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="39307-117">Som standard tilldelas den här rollen till rollgrupperna **Organisationshantering** (Globala administratörer), **karantänadministratör**och **Säkerhetsadministratör** i säkerhets- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="39307-117">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="39307-118">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="39307-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="39307-119">Meddelanden i karantän behålls under en standardperiod innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="39307-119">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="39307-120">Meddelanden i karantän av policyer mot skräppost (skräppost, nätfiske och massmeddelande): 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="39307-120">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="39307-121">Detta är standard- och maxvärdet.</span><span class="sxs-lookup"><span data-stu-id="39307-121">This is the default and maximum value.</span></span> <span data-ttu-id="39307-122">Mer om du vill konfigurera det här värdet finns i [Konfigurera principer mot skräppost](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="39307-122">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="39307-123">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="39307-123">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="39307-124">Meddelanden som innehåller skadlig kod: 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="39307-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="39307-125">När ett meddelande upphör att gälla från karantänen kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="39307-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="39307-126">Använda Security & Compliance Center för att hantera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="39307-127">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-127">View quarantined email</span></span>

1. <span data-ttu-id="39307-128">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="39307-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="39307-129">Kontrollera att **Visa i karantän** är inställt på standardvärdet **e-post**.</span><span class="sxs-lookup"><span data-stu-id="39307-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="39307-130">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="39307-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="39307-131">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="39307-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="39307-132">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="39307-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="39307-133">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-134">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-135">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-136">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-137">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-138">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-138">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="39307-139">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="39307-139">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="39307-140">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="39307-140">**Recipient**</span></span>

   - <span data-ttu-id="39307-141">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="39307-141">**Message ID**</span></span>

   - <span data-ttu-id="39307-142">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="39307-142">**Policy name**</span></span>

   - <span data-ttu-id="39307-143">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="39307-143">**Size**</span></span>

   - <span data-ttu-id="39307-144">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="39307-144">**Direction**</span></span>

   <span data-ttu-id="39307-145">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="39307-145">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="39307-146">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="39307-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="39307-147">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="39307-147">The available filters are:</span></span>

   - <span data-ttu-id="39307-148">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="39307-148">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="39307-149">**I dag**</span><span class="sxs-lookup"><span data-stu-id="39307-149">**Today**</span></span>

     - <span data-ttu-id="39307-150">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="39307-150">**Next 2 days**</span></span>

     - <span data-ttu-id="39307-151">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="39307-151">**Next 7 days**</span></span>

     - <span data-ttu-id="39307-152">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="39307-152">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="39307-153">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="39307-153">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="39307-154">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="39307-154">**Quarantine reason**:</span></span>

     - <span data-ttu-id="39307-155">**Princip**: Meddelandet matchade villkoren för en regel för e-postflöde (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="39307-155">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="39307-156">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="39307-156">**Bulk**</span></span>

     - <span data-ttu-id="39307-157">**Phish**</span><span class="sxs-lookup"><span data-stu-id="39307-157">**Phish**</span></span>

     - <span data-ttu-id="39307-158">**Malware**</span><span class="sxs-lookup"><span data-stu-id="39307-158">**Malware**</span></span>

     - <span data-ttu-id="39307-159">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="39307-159">**Spam**</span></span>

     - <span data-ttu-id="39307-160">**Högt förtroende Phish**</span><span class="sxs-lookup"><span data-stu-id="39307-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="39307-161">**E-postmottagare**: Alla användare eller endast meddelanden som skickas till dig.</span><span class="sxs-lookup"><span data-stu-id="39307-161">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="39307-162">Slutanvändare kan bara hantera meddelanden i karantän som skickas till dem.</span><span class="sxs-lookup"><span data-stu-id="39307-162">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="39307-163">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="39307-163">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="39307-164">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="39307-164">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="39307-165">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="39307-165">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="39307-166">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="39307-166">Wildcards aren't supported.</span></span> <span data-ttu-id="39307-167">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="39307-167">You can search by the following values:</span></span>

   - <span data-ttu-id="39307-168">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="39307-168">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="39307-169">Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du bestämmer att meddelandet sattes i karantän i stället för levererat.</span><span class="sxs-lookup"><span data-stu-id="39307-169">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="39307-170">Var noga med att inkludera det fullständiga meddelande-ID-värdet, som kan innehålla vinkelparenteser (\<\>).</span><span class="sxs-lookup"><span data-stu-id="39307-170">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="39307-171">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="39307-171">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="39307-172">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="39307-172">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="39307-173">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="39307-173">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="39307-174">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="39307-174">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="39307-175">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="39307-175">The search is not case-sensitive.</span></span>

   <span data-ttu-id="39307-176">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="39307-176">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="39307-177">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="39307-177">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="39307-178">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="39307-178">Export message results</span></span>

1. <span data-ttu-id="39307-179">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="39307-179">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="39307-180">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="39307-180">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="39307-181">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="39307-181">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="39307-182">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-182">View quarantined message details</span></span>

<span data-ttu-id="39307-183">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="39307-183">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="39307-184">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="39307-184">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="39307-185">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="39307-185">**Sender address**</span></span>

- <span data-ttu-id="39307-186">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="39307-186">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="39307-187">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="39307-187">**Subject**</span></span>

- <span data-ttu-id="39307-188">**Karantänorsak**: Visar om ett meddelande har identifierats som **Skräppost,** **Bulk,** **Phish**, matchade en regel för e-postflöde (**transportregel**) eller har identifierats som innehållande **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="39307-188">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="39307-189">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="39307-189">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="39307-190">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="39307-190">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="39307-191">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="39307-191">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="39307-192">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="39307-192">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="39307-193">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-193">Take action on quarantined email</span></span>

<span data-ttu-id="39307-194">När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="39307-194">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="39307-195">**Utgivningsmeddelande:** I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="39307-195">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="39307-196">**Rapportera meddelanden till Microsoft för analys**: Detta är markerat som standard och rapporterar det felaktigt i karantän meddelandet till Microsoft som ett falskt positivt.</span><span class="sxs-lookup"><span data-stu-id="39307-196">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="39307-197">Om meddelandet har satts i karantän som skräppost, bulk, nätfiske eller skadlig kod rapporteras meddelandet också till Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="39307-197">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="39307-198">Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet kan skickas igenom.</span><span class="sxs-lookup"><span data-stu-id="39307-198">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="39307-199">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="39307-199">Choose one of the following options:</span></span>

    - <span data-ttu-id="39307-200">**Släpp meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="39307-200">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="39307-201">**Släpp meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="39307-201">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="39307-202">**Släpp meddelanden till andra**</span><span class="sxs-lookup"><span data-stu-id="39307-202">**Release messages to other people**</span></span>

  <span data-ttu-id="39307-203">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="39307-203">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="39307-204">Anteckningar om att släppa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="39307-204">Notes about releasing messages:</span></span>

  - <span data-ttu-id="39307-205">Du kan inte släppa ett meddelande till samma mottagare mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="39307-205">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="39307-206">Endast mottagare som inte har tagit emot meddelandet visas i listan över potentiella mottagare.</span><span class="sxs-lookup"><span data-stu-id="39307-206">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="39307-207">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="39307-207">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="39307-208">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="39307-208">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="39307-209">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="39307-209">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="39307-210">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="39307-210">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="39307-211">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="39307-211">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="39307-212">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="39307-212">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="39307-213">**Ta bort från karantänen**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="39307-213">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="39307-214">**Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="39307-214">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="39307-215">**Skicka meddelande**: I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="39307-215">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="39307-216">**Objekttyp**: **E-post** (standard), **URL**eller **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="39307-216">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="39307-217">**Inlämningsformat**: **Nätverksmeddelande-ID** (standard, med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller **Arkiv** (bläddra till en lokal EML- eller MSG-fil).</span><span class="sxs-lookup"><span data-stu-id="39307-217">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="39307-218">Observera att om du väljer **Arkiv** och sedan väljer **Nätverksmeddelande-ID**är det ursprungliga värdet borta.</span><span class="sxs-lookup"><span data-stu-id="39307-218">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="39307-219">**Mottagare**: Skriv vid lån en ursprunglig mottagare av meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="39307-219">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="39307-220">Du kan också klicka på **Markera alla** och sedan selektivt ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="39307-220">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="39307-221">**Orsak till inlämning:** **Bör inte ha blockerats** (standard) eller **Bör ha blockerats**.</span><span class="sxs-lookup"><span data-stu-id="39307-221">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="39307-222">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="39307-222">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="39307-223">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="39307-223">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="39307-224">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-224">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="39307-225">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="39307-225">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="39307-226">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="39307-226">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="39307-227">**Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="39307-227">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="39307-228">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="39307-228">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="39307-229">Endast ATP: Använd Security & Compliance Center för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-229">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="39307-230">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för ATP Plan 1- och Plan 2-prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="39307-230">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="39307-231">I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39307-231">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="39307-232">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-232">View quarantined files</span></span>

1. <span data-ttu-id="39307-233">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="39307-233">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="39307-234">Ändra **vy i karantän** till standardvärdefilerna . **files**</span><span class="sxs-lookup"><span data-stu-id="39307-234">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="39307-235">Du kan sortera i ett fält genom att klicka på ett tillgängligt kolumnhuvud.</span><span class="sxs-lookup"><span data-stu-id="39307-235">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="39307-236">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="39307-236">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="39307-237">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="39307-237">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="39307-238">Standardkolumnerna är markerade med<sup>\*</sup>en asterisk ( ):</span><span class="sxs-lookup"><span data-stu-id="39307-238">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="39307-239">**Användaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-239">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-240">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-240">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-241">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-241">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-242">**URL för filer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-242">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-243">**Filstorlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-243">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-244">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-244">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-245">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="39307-245">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="39307-246">**Detekteras av**</span><span class="sxs-lookup"><span data-stu-id="39307-246">**Detected by**</span></span>

   - <span data-ttu-id="39307-247">**Ändrad med tiden**</span><span class="sxs-lookup"><span data-stu-id="39307-247">**Modified by time**</span></span>

4. <span data-ttu-id="39307-248">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="39307-248">To filter the results, click **Filter**.</span></span> <span data-ttu-id="39307-249">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="39307-249">The available filters are:</span></span>

   - <span data-ttu-id="39307-250">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="39307-250">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="39307-251">**I dag**</span><span class="sxs-lookup"><span data-stu-id="39307-251">**Today**</span></span>

     - <span data-ttu-id="39307-252">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="39307-252">**Next 2 days**</span></span>

     - <span data-ttu-id="39307-253">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="39307-253">**Next 7 days**</span></span>

     - <span data-ttu-id="39307-254">Ett anpassat datum-/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="39307-254">A custom date/time range.</span></span>

   - <span data-ttu-id="39307-255">**Mottagen tid**</span><span class="sxs-lookup"><span data-stu-id="39307-255">**Received time**</span></span>

   - <span data-ttu-id="39307-256">**Karantän orsak:** Det enda tillgängliga värdet är **Malware**.</span><span class="sxs-lookup"><span data-stu-id="39307-256">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="39307-257">När du har hittat en viss fil i karantän markerar du filen för att visa information om den och vidtar åtgärder för den (till exempel visa, släpp, hämta eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="39307-257">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="39307-258">Exportera filresultat</span><span class="sxs-lookup"><span data-stu-id="39307-258">Export file results</span></span>

1. <span data-ttu-id="39307-259">Markera de filer du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="39307-259">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="39307-260">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="39307-260">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="39307-261">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="39307-261">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="39307-262">Visa filinformation i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-262">View quarantined file details</span></span>

<span data-ttu-id="39307-263">När du markerar en fil i listan visas följande filinformation i fönstret **Utfällbara information:**</span><span class="sxs-lookup"><span data-stu-id="39307-263">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="39307-264">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="39307-264">**File Name**</span></span>

- <span data-ttu-id="39307-265">**Fil-URL**: URL som definierar platsen för filen (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="39307-265">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="39307-266">**Skadligt innehåll har upptäckts på** Datum/tid då filen sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="39307-266">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="39307-267">**Upphör att gälla**: Det datum då filen tas bort från karantänen.</span><span class="sxs-lookup"><span data-stu-id="39307-267">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="39307-268">**Detekteras av:** ATP (Advanced Threat Protection) eller Microsofts anti-malware-motor.</span><span class="sxs-lookup"><span data-stu-id="39307-268">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="39307-269">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="39307-269">**Released?**</span></span>

- <span data-ttu-id="39307-270">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="39307-270">**Malware Name**</span></span>

- <span data-ttu-id="39307-271">**Dokument-ID:** En unik identifierare för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="39307-271">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="39307-272">**Filstorlek:** I kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="39307-272">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="39307-273">**Organisation** Organisationens unika ID.</span><span class="sxs-lookup"><span data-stu-id="39307-273">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="39307-274">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="39307-274">**Last modified**</span></span>

- <span data-ttu-id="39307-275">**Ändrad av**: Användaren som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="39307-275">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="39307-276">**Värde för säker hashalgoritm 256-bitars (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra ryktesbutiker eller på andra platser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="39307-276">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="39307-277">Vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-277">Take action on quarantined files</span></span>

<span data-ttu-id="39307-278">När du väljer en fil i listan kan du vidta följande åtgärder för filen i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="39307-278">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="39307-279">**Släpp filer**: Markera (standard) eller avmarkera **rapportfiler till Microsoft för analys**och klicka sedan på Släpp **filer**.</span><span class="sxs-lookup"><span data-stu-id="39307-279">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="39307-280">**Ladda ner fil**</span><span class="sxs-lookup"><span data-stu-id="39307-280">**Download file**</span></span>

- <span data-ttu-id="39307-281">**Ta bort fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="39307-281">**Remove file from quarantine**</span></span>

<span data-ttu-id="39307-282">Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="39307-282">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="39307-283">Åtgärder på filer i flera karantäner</span><span class="sxs-lookup"><span data-stu-id="39307-283">Actions on multiple quarantined files</span></span>

<span data-ttu-id="39307-284">När du väljer flera filer i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="39307-284">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="39307-285">**Släpp filer**</span><span class="sxs-lookup"><span data-stu-id="39307-285">**Release files**</span></span>

- <span data-ttu-id="39307-286">**Ta bort filer**: När du klickar på **Ja** i varningen som visas tas filerna omedelbart bort.</span><span class="sxs-lookup"><span data-stu-id="39307-286">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="39307-287">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="39307-287">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="39307-288">Använda Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att visa och hantera meddelanden och filer i karantän</span><span class="sxs-lookup"><span data-stu-id="39307-288">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="39307-289">De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:</span><span class="sxs-lookup"><span data-stu-id="39307-289">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="39307-290">Ta bort karantänMessage</span><span class="sxs-lookup"><span data-stu-id="39307-290">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="39307-291">Exportera karantänMessage</span><span class="sxs-lookup"><span data-stu-id="39307-291">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="39307-292">Hämta karantänMessage</span><span class="sxs-lookup"><span data-stu-id="39307-292">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="39307-293">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observera att den här cmdleten endast är för meddelanden, inte skadliga programfiler från ATP för SharePoint Online, OneDrive för företag eller Teams.</span><span class="sxs-lookup"><span data-stu-id="39307-293">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="39307-294">Release-KarantänMessage</span><span class="sxs-lookup"><span data-stu-id="39307-294">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
