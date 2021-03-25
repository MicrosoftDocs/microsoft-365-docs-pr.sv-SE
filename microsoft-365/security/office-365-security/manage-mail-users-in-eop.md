---
title: Hantera e-postanvändare i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Läs mer om hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive hur du hanterar användare med katalogsynkronisering, EAC och PowerShell.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207021"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="f613c-103">Hantera e-postanvändare i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="f613c-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f613c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f613c-104">**Applies to**</span></span>
-  [<span data-ttu-id="f613c-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="f613c-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f613c-106">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är e-postanvändare den grundläggande typen av användarkonto.</span><span class="sxs-lookup"><span data-stu-id="f613c-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="f613c-107">En e-postanvändare har kontouppgifter i den fristående EOP-organisationen och kan komma åt resurser (har tilldelats behörigheter).</span><span class="sxs-lookup"><span data-stu-id="f613c-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="f613c-108">En e-postanvändares e-postadress är extern (till exempel i din lokala e-postmiljö).</span><span class="sxs-lookup"><span data-stu-id="f613c-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="f613c-109">När du skapar en e-postanvändare är motsvarande användarkonto tillgängligt i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f613c-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f613c-110">När du skapar ett användarkonto i administrationscentret för Microsoft 365 kan du inte använda det kontot till att skapa en e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="f613c-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="f613c-111">Den rekommenderade metoden för att skapa och hantera e-postanvändare i [](#use-directory-synchronization-to-manage-mail-users) fristående EOP är att använda katalogsynkronisering enligt beskrivningen i avsnittet Använda katalogsynkronisering för att hantera e-postanvändare längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f613c-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="f613c-112">För fristående EOP-organisationer med ett litet antal användare kan du lägga till och hantera e-postanvändare i Administrationscenter för Exchange (EAC) eller i fristående EOP PowerShell enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f613c-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f613c-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f613c-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f613c-114">Information om hur du öppnar administrationscentret för Exchange (EAC) finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f613c-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f613c-115">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f613c-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f613c-116">När du skapar e-postanvändare i EOP PowerShell kan det uppstå begränsningar.</span><span class="sxs-lookup"><span data-stu-id="f613c-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="f613c-117">Dessutom använder EOP PowerShell-cmdlets en batchbearbetningsmetod som resulterar i en fördröjning på några minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="f613c-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="f613c-118">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f613c-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f613c-119">Specifikt behöver du rollerna Skapa **(skapa)** och E-postmottagare **(ändra),** som tilldelas rollgrupperna Organisationshantering **(globala** administratörer) och Mottagarhantering som standard. </span><span class="sxs-lookup"><span data-stu-id="f613c-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="f613c-120">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="f613c-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f613c-121">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="f613c-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f613c-122">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="f613c-122">Having problems?</span></span> <span data-ttu-id="f613c-123">Be om hjälp i Exchange-forumen.</span><span class="sxs-lookup"><span data-stu-id="f613c-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="f613c-124">Gå till [Exchange Online Protection-forumet.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="f613c-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="f613c-125">Använda Exchange admin center för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="f613c-126">Använda EAC för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="f613c-127">Gå till Mottagarnas kontakter **i** EAC \> </span><span class="sxs-lookup"><span data-stu-id="f613c-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="f613c-128">Klicka **på ny** ny ikon ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f613c-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f613c-129">På sidan **Ny e-postanvändare** som öppnas konfigurerar du följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="f613c-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="f613c-130">Inställningar som är markerade med <sup>\*</sup> ett är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="f613c-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="f613c-131">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="f613c-131">**First name**</span></span>

   - <span data-ttu-id="f613c-132">**Initialer:** Personens initial för mellannamn.</span><span class="sxs-lookup"><span data-stu-id="f613c-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="f613c-133">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="f613c-133">**Last name**</span></span>

   - <span data-ttu-id="f613c-134"><sup>\*</sup>**Visningsnamn:** Som standard visas värdena från rutorna **Förnamn,** **Initialer** **och Efternamn.**</span><span class="sxs-lookup"><span data-stu-id="f613c-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="f613c-135">Du kan acceptera eller ändra det här värdet.</span><span class="sxs-lookup"><span data-stu-id="f613c-135">You can accept this value or change it.</span></span> <span data-ttu-id="f613c-136">Värdet ska vara unikt och får vara högst 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="f613c-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="f613c-137"><sup>\*</sup>**Alias:** Ange ett unikt alias, upp till 64 tecken, för användaren</span><span class="sxs-lookup"><span data-stu-id="f613c-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="f613c-138">**Extern e-postadress:** Ange användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="f613c-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="f613c-139">Domänen ska vara extern i den molnbaserade organisationen.</span><span class="sxs-lookup"><span data-stu-id="f613c-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="f613c-140"><sup>\*</sup>**Användar-ID:** Ange det konto som personen kommer att använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f613c-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="f613c-141">Användar-ID består av ett användarnamn till vänster om at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="f613c-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="f613c-142"><sup>\*</sup>**Nytt lösenord** <sup>\*</sup> **och Bekräfta lösenordet:** Ange och skriv lösenordet för kontot igen.</span><span class="sxs-lookup"><span data-stu-id="f613c-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="f613c-143">Kontrollera att lösenordet uppfyller kraven på lösenordslängd, komplexitet och historik för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f613c-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="f613c-144">När du är klar klickar du på Spara **för att** skapa e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="f613c-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="f613c-145">Använda EAC för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="f613c-146">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="f613c-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="f613c-147">Markera den e-postanvändare som du vill ändra och klicka sedan på **redigera** ![ redigeringsikonen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f613c-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="f613c-148">På sidan för e-postanvändares egenskaper som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="f613c-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="f613c-149">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f613c-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="f613c-150">Allmänt</span><span class="sxs-lookup"><span data-stu-id="f613c-150">General</span></span>

<span data-ttu-id="f613c-151">Använd fliken **Allmänt om** du vill visa eller ändra grundläggande information om e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="f613c-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="f613c-152">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="f613c-152">**First name**</span></span>

- <span data-ttu-id="f613c-153">**Initialer**</span><span class="sxs-lookup"><span data-stu-id="f613c-153">**Initials**</span></span>

- <span data-ttu-id="f613c-154">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="f613c-154">**Last name**</span></span>

- <span data-ttu-id="f613c-155">**Visningsnamn:** Det här namnet visas i organisationens adressbok, på raderna Till och Från i e-postmeddelanden och i listan över kontakter i EAC.</span><span class="sxs-lookup"><span data-stu-id="f613c-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="f613c-156">Namnet får inte innehålla tomma blanksteg före eller efter visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="f613c-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="f613c-157">**Användar-ID:** Det här är användarens konto i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f613c-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="f613c-158">Du kan inte ändra det här värdet här.</span><span class="sxs-lookup"><span data-stu-id="f613c-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="f613c-159">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="f613c-159">Contact information</span></span>

<span data-ttu-id="f613c-160">Använd fliken **Kontaktinformation** för att visa eller ändra användarens kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="f613c-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="f613c-161">Informationen på den här sidan visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="f613c-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="f613c-162">**Gata**</span><span class="sxs-lookup"><span data-stu-id="f613c-162">**Street**</span></span>
- <span data-ttu-id="f613c-163">**Ort**</span><span class="sxs-lookup"><span data-stu-id="f613c-163">**City**</span></span>
- <span data-ttu-id="f613c-164">**Delstat/provins**</span><span class="sxs-lookup"><span data-stu-id="f613c-164">**State/Province**</span></span>
- <span data-ttu-id="f613c-165">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="f613c-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="f613c-166">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="f613c-166">**Country/Region**</span></span>
- <span data-ttu-id="f613c-167">**Telefon, arbete**</span><span class="sxs-lookup"><span data-stu-id="f613c-167">**Work phone**</span></span>
- <span data-ttu-id="f613c-168">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="f613c-168">**Mobile phone**</span></span>
- <span data-ttu-id="f613c-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="f613c-169">**Fax**</span></span>
- <span data-ttu-id="f613c-170">**Fler alternativ**</span><span class="sxs-lookup"><span data-stu-id="f613c-170">**More options**</span></span>

  - <span data-ttu-id="f613c-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="f613c-171">**Office**</span></span>
  - <span data-ttu-id="f613c-172">**Telefon hem**</span><span class="sxs-lookup"><span data-stu-id="f613c-172">**Home phone**</span></span>
  - <span data-ttu-id="f613c-173">**Webbsida**</span><span class="sxs-lookup"><span data-stu-id="f613c-173">**Web page**</span></span>
  - <span data-ttu-id="f613c-174">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="f613c-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="f613c-175">Organisation</span><span class="sxs-lookup"><span data-stu-id="f613c-175">Organization</span></span>

<span data-ttu-id="f613c-176">Använd fliken **Organisation** om du vill spela in detaljerad information om användarens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f613c-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="f613c-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="f613c-177">**Title**</span></span>
- <span data-ttu-id="f613c-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="f613c-178">**Department**</span></span>
- <span data-ttu-id="f613c-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="f613c-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="f613c-180">Använda EAC för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="f613c-181">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="f613c-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="f613c-182">Markera den e-postanvändare du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="f613c-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="f613c-183">Använda PowerShell för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="f613c-184">Använda fristående EOP PowerShell för att visa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="f613c-185">Om du vill returnera en sammanfattningslista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f613c-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="f613c-186">Om du vill visa detaljerad information om en viss e-postanvändare ersätter du med namnet, alias eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f613c-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="f613c-187">Detaljerad information om syntax och parametrar finns i [Hämta mottagare](/powershell/module/exchange/get-recipient) och [Hämta användare.](/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="f613c-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="f613c-188">Använda fristående EOP PowerShell för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="f613c-189">Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f613c-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="f613c-190">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="f613c-190">**Notes**:</span></span>

- <span data-ttu-id="f613c-191">Parametern _Name_ är obligatorisk, har en maxlängd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="f613c-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="f613c-192">Om du inte använder _parametern DisplayName_ används värdet för _parametern Name_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="f613c-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="f613c-193">Om du inte använder _aliasparametern_ används vänster sida av _MicrosoftOnlineServicesID-parametern_ för aliaset.</span><span class="sxs-lookup"><span data-stu-id="f613c-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="f613c-194">Om du inte använder _parametern ExternalEmailAddress_ används _värdet för MicrosoftOnlineServicesID_ för den externa e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="f613c-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="f613c-195">I det här exemplet skapas en e-postanvändare med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f613c-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="f613c-196">Det här namnet ärZenZeng och visningsnamnet är Zen Zeng.</span><span class="sxs-lookup"><span data-stu-id="f613c-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="f613c-197">Förnamnet är Zeng och efternamnet är Zeng.</span><span class="sxs-lookup"><span data-stu-id="f613c-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="f613c-198">Aliaset är alias.</span><span class="sxs-lookup"><span data-stu-id="f613c-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="f613c-199">Den externa e-postadressen är jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="f613c-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="f613c-200">Kontonamnet är jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="f613c-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="f613c-201">Lösenordet är Pa$$word 1.</span><span class="sxs-lookup"><span data-stu-id="f613c-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="f613c-202">Detaljerad information om syntax och parametrar finns i [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="f613c-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="f613c-203">Använda fristående EOP PowerShell för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="f613c-204">Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f613c-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="f613c-205">I det här exemplet anges den externa e-postadressen för Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="f613c-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="f613c-206">I det här exemplet sätts företagsegenskapen för alla e-postanvändare till Contoso.</span><span class="sxs-lookup"><span data-stu-id="f613c-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="f613c-207">Detaljerad information om syntax och parametrar finns i [Set-EOPMailUser.](/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="f613c-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="f613c-208">Använda fristående EOP PowerShell för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="f613c-209">Om du vill ta bort e-postanvändare i fristående EOP PowerShell ersätter du med namnet, aliaset eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f613c-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="f613c-210">I det här exemplet tas e-postanvändaren för Zen Zeng bort.</span><span class="sxs-lookup"><span data-stu-id="f613c-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="f613c-211">Detaljerad information om syntax och parametrar finns i [Remove-EOPMailUser.](/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="f613c-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f613c-212">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="f613c-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="f613c-213">Kontrollera att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP genom att använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="f613c-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="f613c-214">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="f613c-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="f613c-215">Kontrollera att e-postanvändaren finns med i listan (eller inte).</span><span class="sxs-lookup"><span data-stu-id="f613c-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="f613c-216">Markera e-postanvändaren och visa informationen i fönstret Information, eller klicka på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f613c-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="f613c-217">I fristående EOP PowerShell kör du följande kommando för att verifiera att e-postanvändaren visas (eller inte visas):</span><span class="sxs-lookup"><span data-stu-id="f613c-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="f613c-218">Ersätt \<MailUserIdentity\> med namnet, alias eller kontonamnet för e-postanvändaren och kör följande kommandon för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="f613c-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="f613c-219">Använda katalogsynkronisering för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="f613c-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="f613c-220">I fristående EOP är katalogsynkronisering tillgänglig för kunder med lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f613c-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="f613c-221">Du kan synkronisera dessa konton till Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="f613c-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="f613c-222">När du synkroniserar dina befintliga användarkonton med Azure Active  Directory kan du visa de användarna i fönstret Mottagare i Exchange admin center (EAC) eller i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f613c-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="f613c-223">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="f613c-223">**Notes**:</span></span>

- <span data-ttu-id="f613c-224">Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i administrationscentret för Microsoft 365, men de synkroniseras inte med din lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f613c-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="f613c-225">Det beror på att katalogsynkronisering bara synkroniserar mottagare från din lokala Active Directory till molnet.</span><span class="sxs-lookup"><span data-stu-id="f613c-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="f613c-226">Vi rekommenderar att du använder katalogsynkronisering för följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="f613c-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="f613c-227">**Listor över betrodda avsändare och spärrade** avsändare i Outlook: När de synkroniseras till tjänsten har de här listorna företräde framför skräppostfiltrering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f613c-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="f613c-228">Då kan användare hantera sina egna listor över Betrodda avsändare och Spärrade avsändare med enskilda avsändare och domänposter.</span><span class="sxs-lookup"><span data-stu-id="f613c-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="f613c-229">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="f613c-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="f613c-230">**Dbeb-blockering (Directory Based Edge Blocking):** Mer information om DBEB finns i Använda katalogbaserad edge-blockering för att avvisa meddelanden som [skickas till ogiltiga mottagare.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="f613c-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="f613c-231">**Åtkomst till karantän för slutanvändarna:** För att komma åt meddelanden i karantän måste mottagarna ha ett giltigt användar-ID och lösenord i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f613c-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="f613c-232">Mer information om karantän finns i [Hitta och släppa meddelanden i karantän som en användare.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f613c-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="f613c-233">E-postflödesregler (kallas även **transportregler):** När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och grupper automatiskt till molnet och du kan sedan skapa e-postflödesregler som är anpassade för specifika användare och/eller grupper utan att du behöver lägga till dem manuellt i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f613c-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="f613c-234">Observera att [dynamiska distributionsgrupper](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="f613c-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="f613c-235">Få nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="f613c-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="f613c-236">Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="f613c-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="f613c-237">Aktivera katalogsynkronisering enligt beskrivningen [i Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="f613c-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="f613c-238">Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen [i Krav för Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="f613c-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="f613c-239">[Välj vilken installationstyp som ska användas för Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="f613c-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="f613c-240">Express</span><span class="sxs-lookup"><span data-stu-id="f613c-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="f613c-241">Anpassad</span><span class="sxs-lookup"><span data-stu-id="f613c-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="f613c-242">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="f613c-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="f613c-243">När du slutför konfigurationsguiden för Azure Active Directory-synkroniseringsverktyget **skapas MSOL_AD_SYNC-kontot** i Active Directory-skogen.</span><span class="sxs-lookup"><span data-stu-id="f613c-243">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="f613c-244">Det här kontot används för att läsa och synkronisera din lokala Active Directory-information.</span><span class="sxs-lookup"><span data-stu-id="f613c-244">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="f613c-245">För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.</span><span class="sxs-lookup"><span data-stu-id="f613c-245">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="f613c-246">När du har konfigurerat synkroniseringen kontrollerar du att AAD Connect synkroniseras korrekt.</span><span class="sxs-lookup"><span data-stu-id="f613c-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="f613c-247">Gå till Mottagare av kontakter **i** EAC och se att listan över användare synkroniserades korrekt från din \>  lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="f613c-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>