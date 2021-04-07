---
title: Hantera meddelanden och filer i karantän som administratör
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Administratörer kan lära sig hur de visar och hanterar meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Microsoft Defender för Office 365 kan också hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dc7fd26d7a81bc76850af4799363c8d17fc1c83
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599541"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="62ded-104">Hantera meddelanden och filer i karantän som administratör i EOP</span><span class="sxs-lookup"><span data-stu-id="62ded-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="62ded-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="62ded-105">**Applies to**</span></span>
- [<span data-ttu-id="62ded-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="62ded-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="62ded-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="62ded-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="62ded-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62ded-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="62ded-109">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="62ded-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="62ded-110">Mer information finns i [EOP i karantän.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="62ded-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="62ded-111">Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="62ded-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="62ded-112">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig programvara, nätfiske med hög säkerhet eller som ett resultat av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="62ded-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="62ded-113">Administratörer kan också rapportera falska positiva resultat till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62ded-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="62ded-114">Administratörer i organisationer med Microsoft Defender för Office 365 kan också visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62ded-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="62ded-115">Du visar och hanterar meddelanden i karantän i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="62ded-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62ded-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="62ded-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62ded-117">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="62ded-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="62ded-118">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="62ded-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="62ded-119">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="62ded-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="62ded-120">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="62ded-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="62ded-121">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="62ded-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="62ded-122">Om du vill vidta åtgärder för meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller  <sup>\*</sup> Karantänadministratör.</span><span class="sxs-lookup"><span data-stu-id="62ded-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="62ded-123">För skrivskyddad åtkomst till meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="62ded-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="62ded-124">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="62ded-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="62ded-125">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="62ded-125">**Notes**:</span></span>

  - <span data-ttu-id="62ded-126">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62ded-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="62ded-127">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="62ded-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="62ded-128">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="62ded-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="62ded-129"><sup>\*</sup>Medlemmar i **rollgruppen Karantänadministratör** måste också  vara medlemmar i rollgruppen hanteringsroll i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) för att kunna göra karantänprocedurer i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62ded-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="62ded-130">Meddelanden i karantän behålls under en standardtid innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="62ded-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="62ded-131">30 dagar för meddelanden som i karantän omfattas av principer mot skräppost (skräppost, nätfiske och massutskick).</span><span class="sxs-lookup"><span data-stu-id="62ded-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="62ded-132">Det här är standardvärdet och maxvärdet.</span><span class="sxs-lookup"><span data-stu-id="62ded-132">This is the default and maximum value.</span></span> <span data-ttu-id="62ded-133">Information om hur du konfigurerar (lägre) det här värdet [finns i Konfigurera principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="62ded-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="62ded-134">15 dagar för meddelanden som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="62ded-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="62ded-135">15 dagar för filer som sätts i karantän av Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams i Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="62ded-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="62ded-136">När ett meddelande förfaller från karantän kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="62ded-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="62ded-137">Använda Säkerhets- & efterlevnadscenter för att hantera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="62ded-138">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-138">View quarantined email</span></span>

1. <span data-ttu-id="62ded-139">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="62ded-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="62ded-140">Kontrollera att **Visa i karantän är** inställt på standardvärdet för e-post. </span><span class="sxs-lookup"><span data-stu-id="62ded-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="62ded-141">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="62ded-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="62ded-142">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="62ded-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="62ded-143">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="62ded-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="62ded-144">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-145">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-146">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-147">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-148">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-149">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-150">**Upphör**</span><span class="sxs-lookup"><span data-stu-id="62ded-150">**Expires**</span></span>
   - <span data-ttu-id="62ded-151">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="62ded-151">**Recipient**</span></span>
   - <span data-ttu-id="62ded-152">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="62ded-152">**Message ID**</span></span>
   - <span data-ttu-id="62ded-153">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="62ded-153">**Policy name**</span></span>
   - <span data-ttu-id="62ded-154">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="62ded-154">**Size**</span></span>
   - <span data-ttu-id="62ded-155">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="62ded-155">**Direction**</span></span>

   <span data-ttu-id="62ded-156">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="62ded-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="62ded-157">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="62ded-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="62ded-158">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="62ded-158">The available filters are:</span></span>

   - <span data-ttu-id="62ded-159">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="62ded-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="62ded-160">**I dag**</span><span class="sxs-lookup"><span data-stu-id="62ded-160">**Today**</span></span>
     - <span data-ttu-id="62ded-161">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="62ded-161">**Next 2 days**</span></span>
     - <span data-ttu-id="62ded-162">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="62ded-162">**Next 7 days**</span></span>
     - <span data-ttu-id="62ded-163">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="62ded-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="62ded-164">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="62ded-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="62ded-165">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="62ded-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="62ded-166">**Princip:** Meddelandet matchade villkoren i en e-postflödesregel (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="62ded-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="62ded-167">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="62ded-167">**Bulk**</span></span>
     - <span data-ttu-id="62ded-168">**Phish:** Skräppostfiltrets  bedömning var nätfiskeskydd eller skydd mot nätfiske i karantän för meddelandet [(förfalskningsinställningar](set-up-anti-phishing-policies.md#spoof-settings) eller [personifieringsskydd).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="62ded-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="62ded-169">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="62ded-169">**Malware**</span></span>
     - <span data-ttu-id="62ded-170">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="62ded-170">**Spam**</span></span>
     - <span data-ttu-id="62ded-171">**Hög konfidensfras**</span><span class="sxs-lookup"><span data-stu-id="62ded-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="62ded-172">**Principtyp**: filtrera meddelanden efter principtyp:</span><span class="sxs-lookup"><span data-stu-id="62ded-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="62ded-173">**Policy mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="62ded-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="62ded-174">**Princip för säkra bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="62ded-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="62ded-175">**Princip för skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="62ded-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="62ded-176">**Filterprincip för värdbaserat innehåll** (Skräppostprincip)</span><span class="sxs-lookup"><span data-stu-id="62ded-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="62ded-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="62ded-177">**Transport rule**</span></span>

   - <span data-ttu-id="62ded-178">**E-postmottagare:** Alla användare eller bara meddelanden som skickats till dig.</span><span class="sxs-lookup"><span data-stu-id="62ded-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="62ded-179">Slutanvändarna kan bara hantera meddelanden i karantän som skickas till dem.</span><span class="sxs-lookup"><span data-stu-id="62ded-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="62ded-180">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="62ded-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="62ded-181">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="62ded-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="62ded-182">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="62ded-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="62ded-183">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="62ded-183">Wildcards aren't supported.</span></span> <span data-ttu-id="62ded-184">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="62ded-184">You can search by the following values:</span></span>

   - <span data-ttu-id="62ded-185">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="62ded-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="62ded-186">Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som har skickats till en användare i organisationen och du anser att meddelandet har satts i karantän i stället för att levereras.</span><span class="sxs-lookup"><span data-stu-id="62ded-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="62ded-187">Se till att ta med det fullständiga värdet för meddelande-ID, vilket kan inkludera vinkelparenteser ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="62ded-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="62ded-188">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="62ded-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="62ded-189">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="62ded-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="62ded-190">**Principnamn**: använd meddelandets hela principnamn.</span><span class="sxs-lookup"><span data-stu-id="62ded-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="62ded-191">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="62ded-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="62ded-192">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="62ded-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="62ded-193">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="62ded-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="62ded-194">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="62ded-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="62ded-195">**Principnamn:** Namnet på principen som ansvarar för att kvartilen av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="62ded-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="62ded-196">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="62ded-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="62ded-197">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="62ded-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="62ded-198">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-198">View quarantined message details</span></span>

<span data-ttu-id="62ded-199">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="62ded-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62ded-200">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="62ded-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="62ded-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="62ded-201">**Sender address**</span></span>

- <span data-ttu-id="62ded-202">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="62ded-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="62ded-203">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="62ded-203">**Subject**</span></span>

- <span data-ttu-id="62ded-204">**Orsak till karantän:** Visar om ett meddelande har identifierats som **skräppost**, **massutskick,** **phish**, matchat en e-postflödesregel **(transportregel)** eller identifierats som innehåller skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="62ded-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="62ded-205">**Antal mottagare**</span><span class="sxs-lookup"><span data-stu-id="62ded-205">**Recipient count**</span></span>

- <span data-ttu-id="62ded-206">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="62ded-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="62ded-207">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="62ded-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="62ded-208">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="62ded-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="62ded-209">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="62ded-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="62ded-210">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-210">Take action on quarantined email</span></span>

<span data-ttu-id="62ded-211">När du har valt ett meddelande kan du välja mellan flera alternativ för vad du vill göra med meddelandena i den **utfällade** rutan Information:</span><span class="sxs-lookup"><span data-stu-id="62ded-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62ded-212">**Släpp meddelande:** I det utfällfönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="62ded-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="62ded-213">**Rapportera meddelanden till Microsoft för analys:** Det här är valt som standard och rapporterar det felaktiga meddelandet till Microsoft som felaktigt positivt.</span><span class="sxs-lookup"><span data-stu-id="62ded-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="62ded-214">Om meddelandet har satts i karantän som skräppost, massutskick, nätfiske eller som innehåller skadlig programvara, rapporteras meddelandet även till Microsofts team för skräppostanalys.</span><span class="sxs-lookup"><span data-stu-id="62ded-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="62ded-215">Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet tillåts.</span><span class="sxs-lookup"><span data-stu-id="62ded-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="62ded-216">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="62ded-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="62ded-217">**Släppa meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="62ded-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="62ded-218">**Släppa meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="62ded-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="62ded-219">**Släpp meddelanden till andra:** Observera att det inte går att släppa skadlig programvara till andra personer än de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="62ded-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="62ded-220">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="62ded-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="62ded-221">Kommentarer om att släppa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="62ded-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="62ded-222">Du kan inte släppa ett meddelande till samma mottagare mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="62ded-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="62ded-223">Endast mottagare som inte har fått meddelandet visas i listan över möjliga mottagare.</span><span class="sxs-lookup"><span data-stu-id="62ded-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="62ded-224">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="62ded-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="62ded-225">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="62ded-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="62ded-226">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="62ded-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="62ded-227">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="62ded-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="62ded-228">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="62ded-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="62ded-229">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="62ded-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="62ded-230">**Ta bort från karantän:** När du **klickar** på Ja i den varning som visas tas meddelandet bort omedelbart utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="62ded-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="62ded-231">**Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="62ded-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="62ded-232">**Spärra avsändare:** Förhindrar avsändaren från att skicka meddelanden till mottagare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="62ded-232">**Block Sender**: Prevents the sender from sending messages to recipients in the organization.</span></span>

- <span data-ttu-id="62ded-233">**Skicka meddelande:** I det utfällfönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="62ded-233">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="62ded-234">**Objekttyp:** **E-post** (standard), **URL** eller **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="62ded-234">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="62ded-235">**Överföringsformat:** **Nätverksmeddelande-ID** (standard med motsvarande värde i rutan Nätverksmeddelande-ID) eller Fil **(bläddra** till en lokal .eml- eller .msg-fil). </span><span class="sxs-lookup"><span data-stu-id="62ded-235">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="62ded-236">Observera att om du väljer **Arkiv** och sedan **Nätverksmeddelande-ID** är det ursprungliga värdet borta.</span><span class="sxs-lookup"><span data-stu-id="62ded-236">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="62ded-237">**Mottagare:** Ange vid leasa en ursprunglig mottagare av meddelandet eller klicka på **Markera alla om** du vill identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="62ded-237">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="62ded-238">Du kan också klicka **på Markera alla** och sedan selektivt ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="62ded-238">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="62ded-239">**Orsak till inskickning:** **Ska inte ha blockerats** (standard) eller Borde **ha blockerats.**</span><span class="sxs-lookup"><span data-stu-id="62ded-239">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="62ded-240">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="62ded-240">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="62ded-241">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="62ded-241">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="62ded-242">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-242">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="62ded-243">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="62ded-243">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="62ded-244">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="62ded-244">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="62ded-245">Tänk dig följande scenario: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="62ded-245">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="62ded-246">Gmail delar upp meddelandet i två kopior som båda skickas till karantän som nätfiske i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62ded-246">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="62ded-247">En administratör släpper båda dessa meddelanden till admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="62ded-247">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="62ded-248">Det första släppta meddelandet som når administratörspostlådan levereras.</span><span class="sxs-lookup"><span data-stu-id="62ded-248">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="62ded-249">Det andra utgivna meddelandet identifieras som dubblettleverans och hoppas över.</span><span class="sxs-lookup"><span data-stu-id="62ded-249">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="62ded-250">Meddelandet identifieras som dubbletter om de har samma meddelande-ID och har fått tid.</span><span class="sxs-lookup"><span data-stu-id="62ded-250">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="62ded-251">**Ta bort** meddelanden: När du **klickar** på Ja i den varning som visas tas meddelandena bort omedelbart utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="62ded-251">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="62ded-252">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="62ded-252">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="62ded-253">Endast Microsoft Defender för Office 365: Använd säkerhets- & och efterlevnadscenter för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-253">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="62ded-254">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för Microsoft Defender för Office 365 abonnemang 1- och abonnemang 2-prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="62ded-254">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="62ded-255">I organisationer med Defender för Office 365 kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62ded-255">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="62ded-256">Information om hur du aktiverar skydd för dessa [filer finns i Aktivera säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="62ded-256">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="62ded-257">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-257">View quarantined files</span></span>

1. <span data-ttu-id="62ded-258">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="62ded-258">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="62ded-259">Ändra **Visa i karantän** till **värdefilerna**.</span><span class="sxs-lookup"><span data-stu-id="62ded-259">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="62ded-260">Du kan sortera på ett fält genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="62ded-260">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="62ded-261">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="62ded-261">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="62ded-262">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="62ded-262">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="62ded-263">Standardkolumnerna är markerade med en asterisk ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="62ded-263">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="62ded-264">**Användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-264">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-265">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-265">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-266">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-266">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-267">**Fil-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-267">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-268">**Filstorlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-268">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-269">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-269">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-270">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62ded-270">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="62ded-271">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="62ded-271">**Detected by**</span></span>
   - <span data-ttu-id="62ded-272">**Ändrad av tid**</span><span class="sxs-lookup"><span data-stu-id="62ded-272">**Modified by time**</span></span>

4. <span data-ttu-id="62ded-273">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="62ded-273">To filter the results, click **Filter**.</span></span> <span data-ttu-id="62ded-274">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="62ded-274">The available filters are:</span></span>

   - <span data-ttu-id="62ded-275">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="62ded-275">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="62ded-276">**I dag**</span><span class="sxs-lookup"><span data-stu-id="62ded-276">**Today**</span></span>
     - <span data-ttu-id="62ded-277">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="62ded-277">**Next 2 days**</span></span>
     - <span data-ttu-id="62ded-278">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="62ded-278">**Next 7 days**</span></span>
     - <span data-ttu-id="62ded-279">Ett anpassat datum-/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="62ded-279">A custom date/time range.</span></span>
   - <span data-ttu-id="62ded-280">**Mottagen tid**</span><span class="sxs-lookup"><span data-stu-id="62ded-280">**Received time**</span></span>
   - <span data-ttu-id="62ded-281">**Orsak till karantän:** Det enda tillgängliga värdet är skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="62ded-281">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="62ded-282">**Principtyp**</span><span class="sxs-lookup"><span data-stu-id="62ded-282">**Policy type**</span></span>

<span data-ttu-id="62ded-283">När du har hittat en viss fil i karantän väljer du filen för att visa information om den och för att vidta åtgärder för den (till exempel visa, släppa, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="62ded-283">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="62ded-284">Visa information om karantänfiler</span><span class="sxs-lookup"><span data-stu-id="62ded-284">View quarantined file details</span></span>

<span data-ttu-id="62ded-285">När du väljer en fil i listan visas  följande filinformation i den utfällade rutan Information:</span><span class="sxs-lookup"><span data-stu-id="62ded-285">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62ded-286">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="62ded-286">**File Name**</span></span>
- <span data-ttu-id="62ded-287">**Fil-URL:** URL som definierar platsen för filen (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="62ded-287">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="62ded-288">**Skadligt innehåll som upptäckts** Datum/tid då filen satt i karantän.</span><span class="sxs-lookup"><span data-stu-id="62ded-288">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="62ded-289">**Går ut:** Det datum då filen tas bort från karantän.</span><span class="sxs-lookup"><span data-stu-id="62ded-289">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="62ded-290">**Upptäckt av**: Defender för Office 365 eller Microsofts motor mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="62ded-290">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="62ded-291">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="62ded-291">**Released?**</span></span>
- <span data-ttu-id="62ded-292">**Malware Name**</span><span class="sxs-lookup"><span data-stu-id="62ded-292">**Malware Name**</span></span>
- <span data-ttu-id="62ded-293">**Dokument-ID:** En unik identifierare för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="62ded-293">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="62ded-294">**Filstorlek:** i kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="62ded-294">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="62ded-295">**Organisation** Organisationens unika ID.</span><span class="sxs-lookup"><span data-stu-id="62ded-295">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="62ded-296">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="62ded-296">**Last modified**</span></span>
- <span data-ttu-id="62ded-297">**Ändrad av:** Den användare som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="62ded-297">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="62ded-298">**256-bitars algoritmen för säker hashalgoritm (SHA-256):** Du kan använda det här hashvärdet för att identifiera filen i andra rykteslager eller på andra platser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="62ded-298">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="62ded-299">Vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-299">Take action on quarantined files</span></span>

<span data-ttu-id="62ded-300">När du väljer en fil i listan kan du utföra  följande åtgärder på filen i den utfällade rutan Information:</span><span class="sxs-lookup"><span data-stu-id="62ded-300">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62ded-301">**Släpp filer:** Markera (standard) eller avmarkera **Rapportfiler till Microsoft för analys** och klicka sedan på Släpp **filer.**</span><span class="sxs-lookup"><span data-stu-id="62ded-301">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="62ded-302">**Ladda ned fil**</span><span class="sxs-lookup"><span data-stu-id="62ded-302">**Download file**</span></span>
- <span data-ttu-id="62ded-303">**Ta bort en fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="62ded-303">**Remove file from quarantine**</span></span>

<span data-ttu-id="62ded-304">Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän löper ut.</span><span class="sxs-lookup"><span data-stu-id="62ded-304">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="62ded-305">Åtgärder för flera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-305">Actions on multiple quarantined files</span></span>

<span data-ttu-id="62ded-306">När du markerar flera filer i karantän i listan (upp till 100) visas den utfällda rutan Massåtgärder där du kan utföra följande åtgärder: </span><span class="sxs-lookup"><span data-stu-id="62ded-306">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="62ded-307">**Släpp filer**</span><span class="sxs-lookup"><span data-stu-id="62ded-307">**Release files**</span></span>
- <span data-ttu-id="62ded-308">**Ta bort** filer: När **du klickar** på Ja i den varning som visas tas filerna bort omedelbart.</span><span class="sxs-lookup"><span data-stu-id="62ded-308">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="62ded-309">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantän</span><span class="sxs-lookup"><span data-stu-id="62ded-309">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="62ded-310">De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:</span><span class="sxs-lookup"><span data-stu-id="62ded-310">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="62ded-311">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62ded-311">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="62ded-312">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62ded-312">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="62ded-313">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62ded-313">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="62ded-314">[Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)Observera att den här cmdleten endast används för meddelanden, inte för bifogade filer i karantän för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62ded-314">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="62ded-315">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62ded-315">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
