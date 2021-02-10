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
description: Lär dig hur du hanterar e-postanvändare i Exchange Online Protection (EOP), bland annat med katalogsynkronisering, EAC och PowerShell för att hantera användare.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166399"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="cda17-103">Hantera e-postanvändare i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="cda17-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cda17-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cda17-104">**Applies to**</span></span>
-  [<span data-ttu-id="cda17-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="cda17-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="cda17-106">I fristående Exchange Online Protection -organisationer (EOP) utan Exchange Online-postlådor är e-postanvändare den grundläggande typen av användarkonto.</span><span class="sxs-lookup"><span data-stu-id="cda17-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="cda17-107">En e-postanvändare har kontoautentiseringsuppgifter i din fristående EOP-organisation och kan komma åt resurser (har tilldelats behörigheter).</span><span class="sxs-lookup"><span data-stu-id="cda17-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="cda17-108">En e-postanvändares e-postadress är extern (till exempel i din lokala e-postmiljö).</span><span class="sxs-lookup"><span data-stu-id="cda17-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="cda17-109">När du skapar en e-postanvändare är motsvarande användarkonto tillgängligt i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cda17-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cda17-110">När du skapar ett användarkonto i administrationscentret för Microsoft 365 kan du inte använda det kontot för att skapa en e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="cda17-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="cda17-111">Den rekommenderade metoden för att skapa och hantera e-postanvändare i [](#use-directory-synchronization-to-manage-mail-users) fristående EOP är att använda katalogsynkronisering enligt beskrivningen i avsnittet Använd katalogsynkronisering för att hantera e-postanvändare senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cda17-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="cda17-112">För fristående EOP-organisationer med ett litet antal användare kan du lägga till och hantera e-postanvändare i administrationscentret för Exchange (EAC) eller i fristående EOP PowerShell enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cda17-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cda17-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cda17-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cda17-114">Om du vill öppna administrationscentret för Exchange (EAC) går du till [administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="cda17-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="cda17-115">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cda17-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cda17-116">När du skapar e-postanvändare i EOP PowerShell kan det uppstå begränsningar.</span><span class="sxs-lookup"><span data-stu-id="cda17-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="cda17-117">Dessutom använder EOP PowerShell-cmdlets en batchbearbetningsmetod som resulterar i en fördröjning på några minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="cda17-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="cda17-118">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cda17-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="cda17-119">Specifikt behöver du rollerna Skapa **(skapa)** och E-postmottagare **(ändra),** som tilldelas rollgrupperna Organisationshantering **(globala** administratörer) och Mottagarhantering som standard. </span><span class="sxs-lookup"><span data-stu-id="cda17-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="cda17-120">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="cda17-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="cda17-121">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="cda17-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="cda17-122">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="cda17-122">Having problems?</span></span> <span data-ttu-id="cda17-123">Be om hjälp i Exchange-forumen.</span><span class="sxs-lookup"><span data-stu-id="cda17-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="cda17-124">Gå till [forumet för Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="cda17-124">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="cda17-125">Använda administrationscentret för Exchange för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="cda17-126">Använda EAC för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="cda17-127">Gå till Mottagare av  kontakter i EAC \> </span><span class="sxs-lookup"><span data-stu-id="cda17-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="cda17-128">Klicka **på ikonen** Nytt ![ ](../../media/ITPro-EAC-AddIcon.png) nytt.</span><span class="sxs-lookup"><span data-stu-id="cda17-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="cda17-129">Konfigurera **följande inställningar på** sidan Ny e-postanvändare som öppnas.</span><span class="sxs-lookup"><span data-stu-id="cda17-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="cda17-130">Inställningar som är markerade med <sup>\*</sup> ett måste.</span><span class="sxs-lookup"><span data-stu-id="cda17-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="cda17-131">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="cda17-131">**First name**</span></span>

   - <span data-ttu-id="cda17-132">**Initialer:** Personens initial för mellannamn.</span><span class="sxs-lookup"><span data-stu-id="cda17-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="cda17-133">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="cda17-133">**Last name**</span></span>

   - <span data-ttu-id="cda17-134"><sup>\*</sup>**Visningsnamn:** Som standard visas värdena från rutorna **Förnamn,** **Initialer** och Efternamn i **den här** rutan.</span><span class="sxs-lookup"><span data-stu-id="cda17-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="cda17-135">Du kan acceptera eller ändra det här värdet.</span><span class="sxs-lookup"><span data-stu-id="cda17-135">You can accept this value or change it.</span></span> <span data-ttu-id="cda17-136">Värdet ska vara unikt och ha en maxlängd på 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="cda17-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="cda17-137"><sup>\*</sup>**Alias:** Ange ett unikt alias, upp till 64 tecken, för användaren</span><span class="sxs-lookup"><span data-stu-id="cda17-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="cda17-138">**Extern e-postadress:** Ange användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="cda17-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="cda17-139">Domänen ska vara extern i den molnbaserade organisationen.</span><span class="sxs-lookup"><span data-stu-id="cda17-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="cda17-140"><sup>\*</sup>**Användar-ID:** Ange det konto som personen kommer att använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cda17-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="cda17-141">Användar-ID består av ett användarnamn till vänster om at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="cda17-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="cda17-142"><sup>\*</sup>**Nytt lösenord** och <sup>\*</sup> **Bekräfta lösenord:** Ange och ange kontolösenordet igen.</span><span class="sxs-lookup"><span data-stu-id="cda17-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="cda17-143">Kontrollera att lösenordet uppfyller kraven för lösenordslängd, komplexitet och historik för din organisation.</span><span class="sxs-lookup"><span data-stu-id="cda17-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="cda17-144">När du är klar klickar du på Spara **för att** skapa e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="cda17-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="cda17-145">Använda EAC för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="cda17-146">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="cda17-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="cda17-147">Markera den e-postanvändare som du vill ändra och klicka sedan på **ikonen** ![ ](../../media/ITPro-EAC-AddIcon.png) Redigera.</span><span class="sxs-lookup"><span data-stu-id="cda17-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="cda17-148">På sidan med egenskaper för e-postanvändare som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="cda17-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="cda17-149">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cda17-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="cda17-150">Allmänt</span><span class="sxs-lookup"><span data-stu-id="cda17-150">General</span></span>

<span data-ttu-id="cda17-151">Använd fliken **Allmänt för** att visa eller ändra grundläggande information om e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="cda17-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="cda17-152">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="cda17-152">**First name**</span></span>

- <span data-ttu-id="cda17-153">**Initialer**</span><span class="sxs-lookup"><span data-stu-id="cda17-153">**Initials**</span></span>

- <span data-ttu-id="cda17-154">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="cda17-154">**Last name**</span></span>

- <span data-ttu-id="cda17-155">**Visningsnamn:** Det här namnet visas i organisationens adressbok, raderna Till och Från i e-postmeddelanden och i listan över kontakter i EAC.</span><span class="sxs-lookup"><span data-stu-id="cda17-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="cda17-156">Namnet får inte innehålla tomma blanksteg före eller efter visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="cda17-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="cda17-157">**Användar-ID:** Det här är användarens konto i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cda17-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="cda17-158">Du kan inte ändra det här värdet här.</span><span class="sxs-lookup"><span data-stu-id="cda17-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="cda17-159">Kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="cda17-159">Contact information</span></span>

<span data-ttu-id="cda17-160">Använd fliken **Kontaktinformation** om du vill visa eller ändra användarens kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="cda17-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="cda17-161">Informationen på den här sidan visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="cda17-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="cda17-162">**Gata**</span><span class="sxs-lookup"><span data-stu-id="cda17-162">**Street**</span></span>
- <span data-ttu-id="cda17-163">**Ort**</span><span class="sxs-lookup"><span data-stu-id="cda17-163">**City**</span></span>
- <span data-ttu-id="cda17-164">**Delstat/provins**</span><span class="sxs-lookup"><span data-stu-id="cda17-164">**State/Province**</span></span>
- <span data-ttu-id="cda17-165">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="cda17-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="cda17-166">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="cda17-166">**Country/Region**</span></span>
- <span data-ttu-id="cda17-167">**Telefon, arbete**</span><span class="sxs-lookup"><span data-stu-id="cda17-167">**Work phone**</span></span>
- <span data-ttu-id="cda17-168">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="cda17-168">**Mobile phone**</span></span>
- <span data-ttu-id="cda17-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="cda17-169">**Fax**</span></span>
- <span data-ttu-id="cda17-170">**Fler alternativ**</span><span class="sxs-lookup"><span data-stu-id="cda17-170">**More options**</span></span>

  - <span data-ttu-id="cda17-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="cda17-171">**Office**</span></span>
  - <span data-ttu-id="cda17-172">**Telefon hem**</span><span class="sxs-lookup"><span data-stu-id="cda17-172">**Home phone**</span></span>
  - <span data-ttu-id="cda17-173">**Webbsida**</span><span class="sxs-lookup"><span data-stu-id="cda17-173">**Web page**</span></span>
  - <span data-ttu-id="cda17-174">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="cda17-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="cda17-175">Organisation</span><span class="sxs-lookup"><span data-stu-id="cda17-175">Organization</span></span>

<span data-ttu-id="cda17-176">Använd fliken **Organisation** om du vill spela in detaljerad information om användarens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cda17-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="cda17-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="cda17-177">**Title**</span></span>
- <span data-ttu-id="cda17-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="cda17-178">**Department**</span></span>
- <span data-ttu-id="cda17-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="cda17-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="cda17-180">Använda EAC för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="cda17-181">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="cda17-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="cda17-182">Markera den e-postanvändare du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="cda17-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="cda17-183">Använda PowerShell för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="cda17-184">Använda fristående EOP PowerShell för att visa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="cda17-185">Om du vill returnera en sammanfattningslista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="cda17-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="cda17-186">Om du vill visa detaljerad information om en viss e-postanvändare ersätter du med namnet, alias eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="cda17-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="cda17-187">Detaljerad information om syntax och parametrar finns [i Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="cda17-187">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="cda17-188">Använda fristående EOP PowerShell för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="cda17-189">Använd följande syntax för att skapa e-postanvändare i fristående EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cda17-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="cda17-190">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="cda17-190">**Notes**:</span></span>

- <span data-ttu-id="cda17-191">_Namnparametern_ är obligatorisk, får innehålla högst 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="cda17-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="cda17-192">Om du inte använder _displayName-parametern_ används värdet för _namnparametern_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="cda17-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="cda17-193">Om du inte använder _aliasparametern_ används vänster sida av _MicrosoftOnlineServicesID-parametern_ för aliaset.</span><span class="sxs-lookup"><span data-stu-id="cda17-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="cda17-194">Om du inte använder _parametern ExternalEmailAddress används_ _värdet i MicrosoftOnlineServicesID_ för den externa e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="cda17-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="cda17-195">I det här exemplet skapas en e-postanvändare med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="cda17-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="cda17-196">The name isZeng and the display name is Zeng.</span><span class="sxs-lookup"><span data-stu-id="cda17-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="cda17-197">Förnamnet är Avg och efternamnet är Zeng.</span><span class="sxs-lookup"><span data-stu-id="cda17-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="cda17-198">Aliaset är kant.</span><span class="sxs-lookup"><span data-stu-id="cda17-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="cda17-199">Den externa e-postadressen jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="cda17-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="cda17-200">Kontonamnet är jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cda17-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="cda17-201">Lösenordet är Pa$$word 1.</span><span class="sxs-lookup"><span data-stu-id="cda17-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="cda17-202">Detaljerad information om syntax och parametrar finns i [New-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="cda17-202">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="cda17-203">Använda fristående EOP PowerShell för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="cda17-204">Använd följande syntax för att ändra befintliga e-postanvändare i fristående EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cda17-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="cda17-205">I det här exemplet anges den externa e-postadressen för Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="cda17-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="cda17-206">I det här exemplet sätts företagsegenskapen för alla e-postanvändare till Contoso.</span><span class="sxs-lookup"><span data-stu-id="cda17-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="cda17-207">Detaljerad information om syntax och parametrar finns i [Set-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="cda17-207">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="cda17-208">Använda fristående EOP PowerShell för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="cda17-209">Om du vill ta bort e-postanvändare i fristående EOP PowerShell ersätter du med namnet, alias eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="cda17-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="cda17-210">I det här exemplet tas e-postanvändaren för Zen Zeng bort.</span><span class="sxs-lookup"><span data-stu-id="cda17-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="cda17-211">Detaljerad information om syntax och parametrar finns i [Remove-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="cda17-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cda17-212">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="cda17-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="cda17-213">Kontrollera att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP genom att använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="cda17-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="cda17-214">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="cda17-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="cda17-215">Kontrollera att e-postanvändaren finns med i listan (eller inte finns med i listan).</span><span class="sxs-lookup"><span data-stu-id="cda17-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="cda17-216">Markera e-postanvändaren och visa informationen i informationsfönstret, eller klicka **på** ![ redigeringsikonen ](../../media/ITPro-EAC-AddIcon.png) för att visa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="cda17-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="cda17-217">I fristående EOP PowerShell kör du följande kommando för att verifiera att e-postanvändaren visas (eller inte visas):</span><span class="sxs-lookup"><span data-stu-id="cda17-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="cda17-218">Ersätt \<MailUserIdentity\> med namnet, alias eller kontonamnet för e-postanvändaren och kör följande kommandon för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="cda17-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="cda17-219">Använda katalogsynkronisering för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="cda17-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="cda17-220">I fristående EOP är katalogsynkronisering tillgänglig för kunder med lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cda17-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="cda17-221">Du kan synkronisera dessa konton till Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="cda17-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="cda17-222">När du synkroniserar dina befintliga användarkonton med Azure Active  Directory kan du visa de användarna i fönstret Mottagare i administrationscentret för Exchange (EAC) eller i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cda17-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="cda17-223">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="cda17-223">**Notes**:</span></span>

- <span data-ttu-id="cda17-224">Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i administrationscentret för Microsoft 365, men de synkroniseras inte med din lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cda17-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="cda17-225">Det beror på att katalogsynkronisering bara synkroniserar mottagare från din lokala Active Directory till molnet.</span><span class="sxs-lookup"><span data-stu-id="cda17-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="cda17-226">Vi rekommenderar att du använder katalogsynkronisering med följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="cda17-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="cda17-227">**Listor över betrodda avsändare och** spärrade avsändare i Outlook: När de synkroniseras till tjänsten har de här listorna företräde framför skräppostfiltrering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cda17-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="cda17-228">Då kan användare hantera sina egna listor över betrodda avsändare och spärrade avsändare med enskilda avsändare och domänposter.</span><span class="sxs-lookup"><span data-stu-id="cda17-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="cda17-229">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="cda17-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="cda17-230">**Dbeb-blockering (Directory Based Edge Blocking):** Mer information om DBEB finns i Använda katalogbaserad edge-blockering för att avvisa meddelanden som skickas [till ogiltiga mottagare.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="cda17-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="cda17-231">**Slutanvändaråtkomst till karantän:** För att få åtkomst till meddelanden i karantän måste mottagarna ha ett giltigt användar-ID och lösenord i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cda17-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="cda17-232">Mer information om karantän finns i [Hitta och släppa meddelanden i karantän som användare.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="cda17-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="cda17-233">E-postflödesregler (kallas även **transportregler)**: När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och grupper automatiskt till molnet, och du kan sedan skapa e-postflödesregler som är anpassade för specifika användare och/eller grupper utan att du måste lägga till dem manuellt i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cda17-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="cda17-234">Observera att [dynamiska distributionsgrupper](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="cda17-234">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="cda17-235">Få nödvändiga behörigheter och förbereda för katalogsynkronisering, enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="cda17-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="cda17-236">Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="cda17-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="cda17-237">Aktivera katalogsynkronisering enligt beskrivningen [i Azure AD Connect-synkronisering: Förstå och anpassa synkronisering.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="cda17-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="cda17-238">Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen i [krav för Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="cda17-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="cda17-239">[Välj vilken installationstyp som ska användas för Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="cda17-239">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="cda17-240">Express</span><span class="sxs-lookup"><span data-stu-id="cda17-240">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="cda17-241">Anpassad</span><span class="sxs-lookup"><span data-stu-id="cda17-241">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="cda17-242">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="cda17-242">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="cda17-243">När du slutför konfigurationsguiden för Azure Active Directory-synkroniseringsverktyget **MSOL_AD_SYNC** kontot i Active Directory-skogen.</span><span class="sxs-lookup"><span data-stu-id="cda17-243">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="cda17-244">Det här kontot används för att läsa och synkronisera din lokala Active Directory-information.</span><span class="sxs-lookup"><span data-stu-id="cda17-244">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="cda17-245">För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.</span><span class="sxs-lookup"><span data-stu-id="cda17-245">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="cda17-246">När du har konfigurerat synkroniseringen kontrollerar du att AAD Connect synkroniseras korrekt.</span><span class="sxs-lookup"><span data-stu-id="cda17-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="cda17-247">Gå till Mottagare av  kontakter i EAC och se att listan över användare har synkroniserats korrekt \>  från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="cda17-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
