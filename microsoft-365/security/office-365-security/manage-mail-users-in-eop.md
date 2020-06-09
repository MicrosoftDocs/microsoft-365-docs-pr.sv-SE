---
title: Hantera e-postanvändare i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Lär dig mer om hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive att använda katalogsynkronisering, EAC och PowerShell för att hantera användare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616840"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="6db17-103">Hantera e-postanvändare i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="6db17-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="6db17-104">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är e-postanvändare den grundläggande typen av användarkonto.</span><span class="sxs-lookup"><span data-stu-id="6db17-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="6db17-105">En e-postanvändare har kontouppgifter i din fristående EOP-organisation och kan komma åt resurser (har tilldelats behörigheter).</span><span class="sxs-lookup"><span data-stu-id="6db17-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="6db17-106">En e-postanvändares e-postadress är extern (till exempel i din lokala e-postmiljö).</span><span class="sxs-lookup"><span data-stu-id="6db17-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="6db17-107">När du skapar en e-postanvändare är motsvarande användarkonto tillgängligt i microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6db17-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6db17-108">När du skapar ett användarkonto i administrationscentret för Microsoft 365 kan du inte använda det kontot för att skapa en e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="6db17-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="6db17-109">Den rekommenderade metoden för att skapa och hantera e-postanvändare i fristående EOP är att använda katalogsynkronisering enligt beskrivningen i avsnittet [Använd katalogsynkronisering för att hantera e-postanvändare](#use-directory-synchronization-to-manage-mail-users) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6db17-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="6db17-110">För fristående EOP-organisationer med ett litet antal användare kan du lägga till och hantera e-postanvändare i Administrationscenter för Exchange (EAC) eller i fristående EOP PowerShell enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6db17-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6db17-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6db17-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6db17-112">Om du vill öppna Administrationscenter för Exchange (EAC) finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6db17-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6db17-113">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6db17-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6db17-114">När du skapar e-postanvändare i EOP PowerShell kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="6db17-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="6db17-115">EOP PowerShell-cmdlets använder också en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona är synliga.</span><span class="sxs-lookup"><span data-stu-id="6db17-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="6db17-116">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="6db17-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6db17-117">Du behöver som standard rollerna För skapande av e-postmottagare (skapa) och E-postmottagare (ändra) som har tilldelats rollgrupperna OrganizationManagement (global admins) och RecipientManagement som standard.</span><span class="sxs-lookup"><span data-stu-id="6db17-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="6db17-118">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6db17-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="6db17-119">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6db17-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6db17-120">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="6db17-120">Having problems?</span></span> <span data-ttu-id="6db17-121">Be om hjälp i Exchange-forumen.</span><span class="sxs-lookup"><span data-stu-id="6db17-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="6db17-122">Besök [forumet för Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="6db17-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="6db17-123">Använda administrationscentret för Exchange för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="6db17-124">Använda EAC för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="6db17-125">Gå till **Mottagare** \> **Kontakter i** EAC</span><span class="sxs-lookup"><span data-stu-id="6db17-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="6db17-126">Klicka på **Ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6db17-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="6db17-127">Konfigurera följande inställningar på **den nya e-postanvändarsidan** som öppnas.</span><span class="sxs-lookup"><span data-stu-id="6db17-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="6db17-128">Inställningar markerade med en <sup>\*</sup> krävs.</span><span class="sxs-lookup"><span data-stu-id="6db17-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="6db17-129">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="6db17-129">**First name**</span></span>

   - <span data-ttu-id="6db17-130">**Initialer**: Personens mellersta initial.</span><span class="sxs-lookup"><span data-stu-id="6db17-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="6db17-131">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="6db17-131">**Last name**</span></span>

   - <span data-ttu-id="6db17-132"><sup>\*</sup>**Visningsnamn**: Som standard visar den här rutan värdena från rutorna **Förnamn,** **Initialer**och **Efternamn.**</span><span class="sxs-lookup"><span data-stu-id="6db17-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="6db17-133">Du kan acceptera det här värdet eller ändra det.</span><span class="sxs-lookup"><span data-stu-id="6db17-133">You can accept this value or change it.</span></span> <span data-ttu-id="6db17-134">Värdet ska vara unikt och ha en maximal längd på 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="6db17-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="6db17-135"><sup>\*</sup>**Alias:** Ange ett unikt alias med upp till 64 tecken för användaren</span><span class="sxs-lookup"><span data-stu-id="6db17-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="6db17-136">**Extern e-postadress**: Ange användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="6db17-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="6db17-137">Domänen ska vara extern till din molnbaserade organisation.</span><span class="sxs-lookup"><span data-stu-id="6db17-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="6db17-138"><sup>\*</sup>**Användar-ID:** Ange det konto som personen ska använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6db17-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="6db17-139">Användar-ID:t består av ett användarnamn till vänster om symbolen at (@) (@) och en domän till höger.</span><span class="sxs-lookup"><span data-stu-id="6db17-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="6db17-140"><sup>\*</sup>**Nytt lösenord** och <sup>\*</sup> **Bekräfta lösenord**: Ange och ange lösenordet igen.</span><span class="sxs-lookup"><span data-stu-id="6db17-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="6db17-141">Kontrollera att lösenordet uppfyller kraven för lösenordslängd, komplexitet och historik i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6db17-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="6db17-142">När du är klar klickar du på **Spara** för att skapa e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="6db17-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="6db17-143">Använda EAC för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="6db17-144">Gå till **Mottagare** \> **kontakter**i EAC.</span><span class="sxs-lookup"><span data-stu-id="6db17-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6db17-145">Markera den e-postanvändare som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-AddIcon.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="6db17-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="6db17-146">På sidan Egenskaper för e-postanvändare som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="6db17-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="6db17-147">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6db17-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="6db17-148">Allmänt</span><span class="sxs-lookup"><span data-stu-id="6db17-148">General</span></span>

<span data-ttu-id="6db17-149">Använd fliken **Allmänt** om du vill visa eller ändra grundläggande information om e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="6db17-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="6db17-150">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="6db17-150">**First name**</span></span>

- <span data-ttu-id="6db17-151">**Initialer**</span><span class="sxs-lookup"><span data-stu-id="6db17-151">**Initials**</span></span>

- <span data-ttu-id="6db17-152">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="6db17-152">**Last name**</span></span>

- <span data-ttu-id="6db17-153">**Visningsnamn**: Det här namnet visas i organisationens adressbok, på raderna Till och Från i e-post och i listan över kontakter i EAC.</span><span class="sxs-lookup"><span data-stu-id="6db17-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="6db17-154">Det här namnet får inte innehålla tomma blanksteg före eller efter visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="6db17-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="6db17-155">**Användar-ID:** Detta är användarens konto i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6db17-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="6db17-156">Du kan inte ändra det här värdet här.</span><span class="sxs-lookup"><span data-stu-id="6db17-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6db17-157">Kontaktuppgifter</span><span class="sxs-lookup"><span data-stu-id="6db17-157">Contact information</span></span>

<span data-ttu-id="6db17-158">Använd fliken **Kontaktinformation** om du vill visa eller ändra användarens kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="6db17-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="6db17-159">Informationen på den här sidan visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="6db17-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="6db17-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="6db17-160">**Street**</span></span>
- <span data-ttu-id="6db17-161">**Ort**</span><span class="sxs-lookup"><span data-stu-id="6db17-161">**City**</span></span>
- <span data-ttu-id="6db17-162">**Stat/provins**</span><span class="sxs-lookup"><span data-stu-id="6db17-162">**State/Province**</span></span>
- <span data-ttu-id="6db17-163">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="6db17-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="6db17-164">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="6db17-164">**Country/Region**</span></span>
- <span data-ttu-id="6db17-165">**Telefon, arbete**</span><span class="sxs-lookup"><span data-stu-id="6db17-165">**Work phone**</span></span>
- <span data-ttu-id="6db17-166">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="6db17-166">**Mobile phone**</span></span>
- <span data-ttu-id="6db17-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="6db17-167">**Fax**</span></span>
- <span data-ttu-id="6db17-168">**Fler alternativ**</span><span class="sxs-lookup"><span data-stu-id="6db17-168">**More options**</span></span>

  - <span data-ttu-id="6db17-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="6db17-169">**Office**</span></span>
  - <span data-ttu-id="6db17-170">**Telefon hem**</span><span class="sxs-lookup"><span data-stu-id="6db17-170">**Home phone**</span></span>
  - <span data-ttu-id="6db17-171">**Webbsida**</span><span class="sxs-lookup"><span data-stu-id="6db17-171">**Web page**</span></span>
  - <span data-ttu-id="6db17-172">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="6db17-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="6db17-173">Organisation</span><span class="sxs-lookup"><span data-stu-id="6db17-173">Organization</span></span>

<span data-ttu-id="6db17-174">Använd fliken **Organisation** om du vill registrera detaljerad information om användarens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6db17-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="6db17-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="6db17-175">**Title**</span></span>
- <span data-ttu-id="6db17-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="6db17-176">**Department**</span></span>
- <span data-ttu-id="6db17-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="6db17-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="6db17-178">Använda EAC för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="6db17-179">Gå till **Mottagare** \> **kontakter**i EAC.</span><span class="sxs-lookup"><span data-stu-id="6db17-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6db17-180">Markera den e-postanvändare som du vill ta bort och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="6db17-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="6db17-181">Använda PowerShell för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="6db17-182">Använda fristående EOP PowerShell för att visa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="6db17-183">Om du vill returnera en sammanfattningslista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="6db17-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="6db17-184">Om du vill visa detaljerad information om en viss e-postanvändare ersätter du \<MailUserIdentity\> med e-postanvändarens namn, alias eller kontonamn och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="6db17-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="6db17-185">Detaljerad syntax- och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [hämta användare](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="6db17-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="6db17-186">Använda fristående EOP PowerShell för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="6db17-187">Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6db17-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="6db17-188">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="6db17-188">**Notes**:</span></span>

- <span data-ttu-id="6db17-189">Parametern _Name_ krävs, har en maximal längd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="6db17-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="6db17-190">Om du inte använder parametern _DisplayName_ används värdet för parametern _Name_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="6db17-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="6db17-191">Om du inte använder parametern _Alias_ används den vänstra sidan av _parametern MicrosoftOnlneServicesID_ för aliaset.</span><span class="sxs-lookup"><span data-stu-id="6db17-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlneServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="6db17-192">Om du inte använder parametern _ExternalEmailAddress_ används _MicrosoftOnlineServicesID-värdet_ för den externa e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="6db17-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="6db17-193">I det här exemplet skapas en e-postanvändare med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6db17-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="6db17-194">Namnet är JeffreyZeng och visningsnamnet är Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="6db17-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="6db17-195">Förnamnet är Jeffrey och efternamnet är Zeng.</span><span class="sxs-lookup"><span data-stu-id="6db17-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="6db17-196">Alias är Jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="6db17-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="6db17-197">Den externa e-postadressen är jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="6db17-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="6db17-198">Kontonamnet är jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6db17-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="6db17-199">Lösenordet är Pa $ $word1.</span><span class="sxs-lookup"><span data-stu-id="6db17-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="6db17-200">Detaljerad syntax- och parameterinformation finns i [Ny-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6db17-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="6db17-201">Använda fristående EOP PowerShell för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="6db17-202">Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6db17-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="6db17-203">I det här exemplet anges den externa e-postadressen för Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="6db17-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="6db17-204">I det här exemplet anges egenskapen Företag för alla e-postanvändare till Contoso.</span><span class="sxs-lookup"><span data-stu-id="6db17-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="6db17-205">Detaljerad syntax- och parameterinformation finns i [Ange-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6db17-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="6db17-206">Använda fristående EOP PowerShell för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="6db17-207">Om du vill ta bort e-postanvändare i fristående EOP PowerShell ersätter du \<MailUserIdentity\> med e-postanvändarens namn, alias eller kontonamn och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="6db17-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="6db17-208">I det här exemplet tas e-postanvändaren bort för Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="6db17-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="6db17-209">Detaljerad syntax- och parameterinformation finns i [Ta bort EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6db17-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6db17-210">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="6db17-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="6db17-211">Om du vill kontrollera att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP använder du något av följande:</span><span class="sxs-lookup"><span data-stu-id="6db17-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="6db17-212">Gå till **Mottagare** \> **kontakter**i EAC.</span><span class="sxs-lookup"><span data-stu-id="6db17-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="6db17-213">Kontrollera att e-postanvändaren finns med i listan (eller inte finns med i listan).</span><span class="sxs-lookup"><span data-stu-id="6db17-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="6db17-214">Markera e-postanvändaren och visa informationen i informationsfönstret eller klicka på **Ikonen Redigera** redigera för att ![ visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6db17-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="6db17-215">I fristående EOP PowerShell kör du följande kommando för att kontrollera att e-postanvändaren finns med i listan (eller inte finns med i listan):</span><span class="sxs-lookup"><span data-stu-id="6db17-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="6db17-216">Ersätt \<MailUserIdentity\> med e-postanvändarens namn, alias eller kontonamn och kör följande kommandon för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="6db17-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="6db17-217">Använda katalogsynkronisering för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="6db17-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="6db17-218">I fristående EOP är katalogsynkronisering tillgänglig för kunder med lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6db17-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="6db17-219">Du kan synkronisera dessa konton till Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="6db17-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="6db17-220">När du synkroniserar dina befintliga användarkonton till Azure Active Directory kan du visa dessa användare i fönstret Mottagare i **Administrationscenter** för Exchange (EAC) eller i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db17-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="6db17-221">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="6db17-221">**Notes**:</span></span>

- <span data-ttu-id="6db17-222">Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i Microsoft 365-administrationscentret, men de synkroniseras inte med den lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6db17-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="6db17-223">Detta beror på att katalogsynkronisering bara synkroniserar mottagare från den lokala Active Directory till molnet.</span><span class="sxs-lookup"><span data-stu-id="6db17-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="6db17-224">Användning av katalogsynkronisering rekommenderas för användning med följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="6db17-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="6db17-225">**Outlook Safe Sender listor och blockerade avsändare listor:** När synkroniseras till tjänsten, dessa listor kommer att ha företräde framför spam filtrering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6db17-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="6db17-226">På så sätt kan användare hantera sin egen lista över betrodda avsändare och blockerad avsändare med enskilda avsändare och domänposter.</span><span class="sxs-lookup"><span data-stu-id="6db17-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="6db17-227">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="6db17-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="6db17-228">**Katalogbaserad kantblockering (DBEB):** Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="6db17-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="6db17-229">**Slutanvändarens åtkomst till karantän:** För att komma åt sina meddelanden i karantän måste mottagarna ha ett giltigt användar-ID och lösenord i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6db17-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="6db17-230">Mer information om karantän finns i [Hitta och släppa meddelanden i karantän som användare](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span><span class="sxs-lookup"><span data-stu-id="6db17-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="6db17-231">**Regler för e-postflöde (kallas även transportregler):** När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och -grupper automatiskt till molnet och du kan sedan skapa regler för e-postflöde som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6db17-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="6db17-232">Observera att [dynamiska distributionsgrupper](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="6db17-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="6db17-233">Hämta nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="6db17-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="6db17-234">Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="6db17-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="6db17-235">Aktivera katalogsynkronisering enligt beskrivningen i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="6db17-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="6db17-236">Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen i [Förutsättningar för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6db17-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="6db17-237">[Välj vilken installationstyp som ska användas för Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="6db17-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="6db17-238">Express</span><span class="sxs-lookup"><span data-stu-id="6db17-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="6db17-239">Anpassade</span><span class="sxs-lookup"><span data-stu-id="6db17-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="6db17-240">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="6db17-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="6db17-241">När du är klar med konfigurationsguiden för Azure Active Directory Sync Tool skapas **MSOL_AD_SYNC-kontot** i Active Directory-skogen.</span><span class="sxs-lookup"><span data-stu-id="6db17-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="6db17-242">Det här kontot används för att läsa och synkronisera din lokala Active Directory-information.</span><span class="sxs-lookup"><span data-stu-id="6db17-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="6db17-243">För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.</span><span class="sxs-lookup"><span data-stu-id="6db17-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="6db17-244">När du har konfigurerat synkroniseringen måste du kontrollera att AAD Connect synkroniseras korrekt.</span><span class="sxs-lookup"><span data-stu-id="6db17-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="6db17-245">I EAC går du till **Mottagare** \> **Kontakter** och visa att listan över användare har synkroniserats korrekt från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="6db17-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
