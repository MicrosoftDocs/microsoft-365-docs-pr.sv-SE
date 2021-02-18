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
description: Administratörer kan lära sig att visa och hantera meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Microsoft Defender för Office 365 kan också hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22bcf0cefb746e92ccadf8254f4076b47ee475c4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287791"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="4222a-104">Hantera meddelanden och filer i karantän som administratör i EOP</span><span class="sxs-lookup"><span data-stu-id="4222a-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4222a-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4222a-105">**Applies to**</span></span>
- [<span data-ttu-id="4222a-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4222a-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4222a-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4222a-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4222a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4222a-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4222a-109">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4222a-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="4222a-110">Mer information finns i [e-postmeddelanden i karantän i EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="4222a-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="4222a-111">Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="4222a-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="4222a-112">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med hög konfidens eller som ett resultat av e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="4222a-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4222a-113">Administratörer kan också rapportera falska positiva resultat till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4222a-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="4222a-114">Administratörer i organisationer med Microsoft Defender för Office 365 kan också visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4222a-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="4222a-115">Du visar och hanterar meddelanden i karantän i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="4222a-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4222a-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4222a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4222a-117">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="4222a-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="4222a-118">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="4222a-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="4222a-119">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4222a-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4222a-120">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4222a-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4222a-121">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="4222a-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4222a-122">Om du vill vidta åtgärder för meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller  <sup>\*</sup> Karantänadministratör.</span><span class="sxs-lookup"><span data-stu-id="4222a-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="4222a-123">För skrivskyddad åtkomst till meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="4222a-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4222a-124">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4222a-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="4222a-125">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="4222a-125">**Notes**:</span></span>

  - <span data-ttu-id="4222a-126">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4222a-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4222a-127">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4222a-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4222a-128">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="4222a-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="4222a-129"><sup>\*</sup>Medlemmar i **rollgruppen för** karantänadministratör måste  också vara medlemmar i rollgruppen Hantering avfrågas i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) för att kunna göra karantänprocedurer i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4222a-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="4222a-130">Meddelanden i karantän behålls under en standardtid innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="4222a-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="4222a-131">30 dagar för meddelanden i karantän enligt principer mot skräppost (skräppost, nätfiske och massutskick).</span><span class="sxs-lookup"><span data-stu-id="4222a-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="4222a-132">Det här är standardvärdet och det högsta värdet.</span><span class="sxs-lookup"><span data-stu-id="4222a-132">This is the default and maximum value.</span></span> <span data-ttu-id="4222a-133">Information om hur du konfigurerar (lägre) det här värdet [finns i Konfigurera principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4222a-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="4222a-134">15 dagar för meddelanden som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4222a-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="4222a-135">15 dagar för filer i karantän efter Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams i Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="4222a-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="4222a-136">När ett meddelande förfaller från karantän kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="4222a-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="4222a-137">Använda Säkerhets- & för att hantera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="4222a-138">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-138">View quarantined email</span></span>

1. <span data-ttu-id="4222a-139">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="4222a-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4222a-140">Kontrollera att **Visa i karantän är** inställt på standardvärdet för e-post. </span><span class="sxs-lookup"><span data-stu-id="4222a-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="4222a-141">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="4222a-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4222a-142">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="4222a-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4222a-143">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="4222a-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4222a-144">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-145">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-146">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-147">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-148">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-149">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-150">**Upphör**</span><span class="sxs-lookup"><span data-stu-id="4222a-150">**Expires**</span></span>
   - <span data-ttu-id="4222a-151">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="4222a-151">**Recipient**</span></span>
   - <span data-ttu-id="4222a-152">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="4222a-152">**Message ID**</span></span>
   - <span data-ttu-id="4222a-153">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="4222a-153">**Policy name**</span></span>
   - <span data-ttu-id="4222a-154">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="4222a-154">**Size**</span></span>
   - <span data-ttu-id="4222a-155">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4222a-155">**Direction**</span></span>

   <span data-ttu-id="4222a-156">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4222a-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="4222a-157">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="4222a-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4222a-158">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4222a-158">The available filters are:</span></span>

   - <span data-ttu-id="4222a-159">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="4222a-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4222a-160">**I dag**</span><span class="sxs-lookup"><span data-stu-id="4222a-160">**Today**</span></span>
     - <span data-ttu-id="4222a-161">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4222a-161">**Next 2 days**</span></span>
     - <span data-ttu-id="4222a-162">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4222a-162">**Next 7 days**</span></span>
     - <span data-ttu-id="4222a-163">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4222a-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4222a-164">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4222a-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4222a-165">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="4222a-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="4222a-166">**Princip:** Meddelandet matchade villkoren i en e-postflödesregel (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="4222a-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="4222a-167">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="4222a-167">**Bulk**</span></span>
     - <span data-ttu-id="4222a-168">**Nätfiske:** Skräppostfiltrets  bedömning var nätfiskeskydd eller skydd mot nätfiske i karantän för meddelandet [(förfalskningsinställningar](set-up-anti-phishing-policies.md#spoof-settings) [eller personifieringsskydd).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4222a-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="4222a-169">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="4222a-169">**Malware**</span></span>
     - <span data-ttu-id="4222a-170">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="4222a-170">**Spam**</span></span>
     - <span data-ttu-id="4222a-171">**Phish med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="4222a-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="4222a-172">**Principtyp**: filtrera meddelanden efter principtyp:</span><span class="sxs-lookup"><span data-stu-id="4222a-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="4222a-173">**Policy för skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="4222a-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="4222a-174">**Princip för säkra bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4222a-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="4222a-175">**Princip för skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="4222a-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="4222a-176">**Filterprincip för värdbaserat innehåll** (Skräppostprincip)</span><span class="sxs-lookup"><span data-stu-id="4222a-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="4222a-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="4222a-177">**Transport rule**</span></span>

   - <span data-ttu-id="4222a-178">**E-postmottagare:** Alla användare eller endast meddelanden som skickats till dig.</span><span class="sxs-lookup"><span data-stu-id="4222a-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="4222a-179">Slutanvändarna kan bara hantera meddelanden i karantän som skickas till dem.</span><span class="sxs-lookup"><span data-stu-id="4222a-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="4222a-180">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="4222a-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4222a-181">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="4222a-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="4222a-182">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4222a-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4222a-183">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="4222a-183">Wildcards aren't supported.</span></span> <span data-ttu-id="4222a-184">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="4222a-184">You can search by the following values:</span></span>

   - <span data-ttu-id="4222a-185">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="4222a-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="4222a-186">Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du fastställer att meddelandet har satts i karantän i stället för att levereras.</span><span class="sxs-lookup"><span data-stu-id="4222a-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="4222a-187">Se till att ta med det fullständiga id-värdet för meddelandet, vilket kan inkludera vinkelparenteser ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="4222a-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="4222a-188">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="4222a-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="4222a-189">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="4222a-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="4222a-190">**Principnamn**: använd meddelandets hela principnamn.</span><span class="sxs-lookup"><span data-stu-id="4222a-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="4222a-191">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="4222a-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4222a-192">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="4222a-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="4222a-193">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="4222a-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4222a-194">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="4222a-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4222a-195">**Principnamn:** Namnet på principen som ansvarar för att kvartilen av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4222a-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="4222a-196">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="4222a-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4222a-197">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="4222a-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="4222a-198">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-198">View quarantined message details</span></span>

<span data-ttu-id="4222a-199">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="4222a-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4222a-200">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="4222a-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="4222a-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4222a-201">**Sender address**</span></span>

- <span data-ttu-id="4222a-202">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="4222a-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="4222a-203">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4222a-203">**Subject**</span></span>

- <span data-ttu-id="4222a-204">**Orsak till** karantän: Visar om ett meddelande har identifierats som **skräppost,** massutskick,  **phish** matchat en e-postflödesregel **(transportregel)** eller identifierats som innehåller skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="4222a-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="4222a-205">**Antal mottagare**</span><span class="sxs-lookup"><span data-stu-id="4222a-205">**Recipient count**</span></span>

- <span data-ttu-id="4222a-206">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="4222a-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="4222a-207">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="4222a-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="4222a-208">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="4222a-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="4222a-209">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="4222a-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4222a-210">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-210">Take action on quarantined email</span></span>

<span data-ttu-id="4222a-211">När du har valt ett meddelande kan du välja mellan flera alternativ för vad du vill göra med meddelandena i den **utfällna** rutan Information:</span><span class="sxs-lookup"><span data-stu-id="4222a-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4222a-212">**Släpp meddelandet:** Välj följande alternativ i det utfällfönster som visas:</span><span class="sxs-lookup"><span data-stu-id="4222a-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4222a-213">**Rapportera meddelanden till Microsoft för analys:** Det här är valt som standard och rapporterar det felaktiga meddelandet i karantän till Microsoft som felaktigt positivt.</span><span class="sxs-lookup"><span data-stu-id="4222a-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="4222a-214">Om meddelandet har satts i karantän som skräppost, massutskick, nätfiske eller som innehåller skadlig programvara rapporteras meddelandet även till Microsofts team för skräppostanalys.</span><span class="sxs-lookup"><span data-stu-id="4222a-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="4222a-215">Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet tillåts.</span><span class="sxs-lookup"><span data-stu-id="4222a-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="4222a-216">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="4222a-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="4222a-217">**Släppa meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="4222a-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="4222a-218">**Släppa meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="4222a-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="4222a-219">**Släpp meddelanden till andra personer:** Observera att det inte går att släppa skadlig programvara till andra personer än de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="4222a-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="4222a-220">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4222a-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="4222a-221">Kommentarer om att släppa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="4222a-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="4222a-222">Du kan inte släppa ett meddelande till samma mottagare fler än en gång.</span><span class="sxs-lookup"><span data-stu-id="4222a-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="4222a-223">Endast mottagare som inte har fått meddelandet visas i listan med potentiella mottagare.</span><span class="sxs-lookup"><span data-stu-id="4222a-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="4222a-224">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="4222a-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4222a-225">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="4222a-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="4222a-226">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="4222a-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4222a-227">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="4222a-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="4222a-228">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="4222a-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="4222a-229">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="4222a-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4222a-230">**Ta bort från karantän:** När du **klickar** på Ja i varningen som visas tas meddelandet bort omedelbart utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="4222a-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="4222a-231">**Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="4222a-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="4222a-232">**Skicka ett** meddelande: Välj följande alternativ i det utfällfönster som visas:</span><span class="sxs-lookup"><span data-stu-id="4222a-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4222a-233">**Objekttyp:** **E-post** (standard), **URL** eller **bifogad fil.**</span><span class="sxs-lookup"><span data-stu-id="4222a-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="4222a-234">**Överföringsformat:** **Nätverksmeddelande-ID** (standard med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller Fil **(bläddra** till en lokal .eml- eller .msg-fil).</span><span class="sxs-lookup"><span data-stu-id="4222a-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="4222a-235">Observera att om du väljer **Arkiv** och sedan **Nätverksmeddelande-ID** är det ursprungliga värdet borta.</span><span class="sxs-lookup"><span data-stu-id="4222a-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="4222a-236">**Mottagare:** Skriv vid leasa en ursprunglig mottagare av meddelandet eller klicka **på Markera alla** för att identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="4222a-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="4222a-237">Du kan också klicka **på Markera alla** och sedan selektivt ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="4222a-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="4222a-238">**Orsak till** **inskickning: Borde inte ha blockerats** (standard) **eller borde ha blockerats.**</span><span class="sxs-lookup"><span data-stu-id="4222a-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="4222a-239">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="4222a-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="4222a-240">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="4222a-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4222a-241">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4222a-242">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4222a-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4222a-243">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="4222a-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4222a-244">Tänk dig följande scenario: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4222a-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="4222a-245">Gmail delar upp det här meddelandet i två kopior som båda dirigeras till karantän som nätfiske i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4222a-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="4222a-246">En administratör släpper båda dessa meddelanden till admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4222a-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="4222a-247">Det första släppta meddelandet som når administratörspostlådan levereras.</span><span class="sxs-lookup"><span data-stu-id="4222a-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="4222a-248">Det andra släppta meddelandet identifieras som dubblettleverans och hoppas över.</span><span class="sxs-lookup"><span data-stu-id="4222a-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="4222a-249">Meddelandet identifieras som dubbletter om de har samma meddelande-ID och tid för mottagna meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4222a-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="4222a-250">**Ta bort** meddelanden: När du klickar på **Ja** i varningen som visas tas meddelandena bort omedelbart utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="4222a-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4222a-251">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4222a-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="4222a-252">Endast Microsoft Defender för Office 365: Använd säkerhets- & för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="4222a-253">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för Microsoft Defender för Office 365 Abonnemang 1- och Abonnemang 2-prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="4222a-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="4222a-254">I organisationer med Defender för Office 365 kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4222a-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="4222a-255">Information om hur du aktiverar skydd för dessa [filer finns i Aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4222a-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="4222a-256">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-256">View quarantined files</span></span>

1. <span data-ttu-id="4222a-257">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="4222a-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4222a-258">Ändra **visa i karantän** till **värdefilerna.**</span><span class="sxs-lookup"><span data-stu-id="4222a-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="4222a-259">Du kan sortera på ett fält genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="4222a-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="4222a-260">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="4222a-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4222a-261">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="4222a-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4222a-262">Standardkolumnerna är markerade med en asterisk ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="4222a-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4222a-263">**Användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-264">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-265">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-266">**Fil-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-267">**Filstorlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-268">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-269">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4222a-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4222a-270">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="4222a-270">**Detected by**</span></span>
   - <span data-ttu-id="4222a-271">**Ändrad efter tid**</span><span class="sxs-lookup"><span data-stu-id="4222a-271">**Modified by time**</span></span>

4. <span data-ttu-id="4222a-272">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="4222a-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4222a-273">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4222a-273">The available filters are:</span></span>

   - <span data-ttu-id="4222a-274">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="4222a-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4222a-275">**I dag**</span><span class="sxs-lookup"><span data-stu-id="4222a-275">**Today**</span></span>
     - <span data-ttu-id="4222a-276">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4222a-276">**Next 2 days**</span></span>
     - <span data-ttu-id="4222a-277">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4222a-277">**Next 7 days**</span></span>
     - <span data-ttu-id="4222a-278">Ett anpassat datum-/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="4222a-278">A custom date/time range.</span></span>
   - <span data-ttu-id="4222a-279">**Mottagen tid**</span><span class="sxs-lookup"><span data-stu-id="4222a-279">**Received time**</span></span>
   - <span data-ttu-id="4222a-280">**Orsak till karantän:** Det enda tillgängliga värdet är skadlig **programvara.**</span><span class="sxs-lookup"><span data-stu-id="4222a-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="4222a-281">**Typ av princip**</span><span class="sxs-lookup"><span data-stu-id="4222a-281">**Policy type**</span></span>

<span data-ttu-id="4222a-282">När du har hittat en specifik fil i karantän väljer du filen för att visa information om den och för att vidta åtgärder på den (till exempel visa, släppa, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="4222a-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="4222a-283">Visa information om karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-283">View quarantined file details</span></span>

<span data-ttu-id="4222a-284">När du väljer en fil i listan visas  följande filinformation i den utfällopanelen Information:</span><span class="sxs-lookup"><span data-stu-id="4222a-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4222a-285">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="4222a-285">**File Name**</span></span>
- <span data-ttu-id="4222a-286">**Fil-URL:** URL som definierar platsen för filen (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="4222a-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="4222a-287">**Skadligt innehåll som upptäckts** Datum/tid då filen satt i karantän.</span><span class="sxs-lookup"><span data-stu-id="4222a-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="4222a-288">**Går ut:** Datumet då filen tas bort från karantän.</span><span class="sxs-lookup"><span data-stu-id="4222a-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="4222a-289">**Upptäckt av:** Defender för Office 365 eller Microsofts motor mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4222a-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="4222a-290">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="4222a-290">**Released?**</span></span>
- <span data-ttu-id="4222a-291">**Malware Name**</span><span class="sxs-lookup"><span data-stu-id="4222a-291">**Malware Name**</span></span>
- <span data-ttu-id="4222a-292">**Dokument-ID:** unik identifierare beskrivning av dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4222a-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="4222a-293">**Filstorlek:** I kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="4222a-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="4222a-294">**Organisation** Din organisations unika ID.</span><span class="sxs-lookup"><span data-stu-id="4222a-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="4222a-295">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="4222a-295">**Last modified**</span></span>
- <span data-ttu-id="4222a-296">**Ändrad av:** Den användare som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="4222a-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="4222a-297">**256-bitars algoritmen för säker hash-algoritm (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra rykteslager eller på andra platser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="4222a-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="4222a-298">Vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-298">Take action on quarantined files</span></span>

<span data-ttu-id="4222a-299">När du väljer en fil i listan kan du utföra  följande åtgärder på filen i den utfällna rutan Information:</span><span class="sxs-lookup"><span data-stu-id="4222a-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4222a-300">**Släpp filer:** Markera (standard) eller avmarkera **rapportfiler till Microsoft för** analys och klicka sedan på **Släpp filer.**</span><span class="sxs-lookup"><span data-stu-id="4222a-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="4222a-301">**Ladda ned fil**</span><span class="sxs-lookup"><span data-stu-id="4222a-301">**Download file**</span></span>
- <span data-ttu-id="4222a-302">**Ta bort en fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="4222a-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="4222a-303">Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän löper ut.</span><span class="sxs-lookup"><span data-stu-id="4222a-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="4222a-304">Åtgärder för flera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="4222a-305">När du markerar flera filer i karantän i listan (upp till 100) visas fönstret Massåtgärder där du kan utföra följande åtgärder: </span><span class="sxs-lookup"><span data-stu-id="4222a-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4222a-306">**Släppa filer**</span><span class="sxs-lookup"><span data-stu-id="4222a-306">**Release files**</span></span>
- <span data-ttu-id="4222a-307">**Ta bort** filer: När du **klickar** på Ja i varningen som visas tas filerna bort direkt.</span><span class="sxs-lookup"><span data-stu-id="4222a-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="4222a-308">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4222a-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="4222a-309">De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:</span><span class="sxs-lookup"><span data-stu-id="4222a-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="4222a-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4222a-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="4222a-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4222a-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="4222a-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4222a-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="4222a-313">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)Observera att den här cmdleten endast används för meddelanden, inte för skadlig programvara från säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4222a-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="4222a-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4222a-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
