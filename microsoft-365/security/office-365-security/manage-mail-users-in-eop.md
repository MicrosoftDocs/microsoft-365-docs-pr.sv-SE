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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Lär dig hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive att använda Directory-synkronisering, UK och PowerShell för att hantera användare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658839"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="50bb2-103">Hantera e-postanvändare i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="50bb2-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="50bb2-104">I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor är e-postanvändarna grundläggande användar konto.</span><span class="sxs-lookup"><span data-stu-id="50bb2-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="50bb2-105">En e-postanvändare har kontoautentiseringsuppgifter i din fristående EOP-organisation och kan komma åt resurser (har tilldelade behörigheter).</span><span class="sxs-lookup"><span data-stu-id="50bb2-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="50bb2-106">E-postadressen till en e-postanvändare är extern (till exempel i din lokala e-postmiljö).</span><span class="sxs-lookup"><span data-stu-id="50bb2-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="50bb2-107">När du skapar en e-postanvändare finns motsvarande användar konto i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50bb2-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="50bb2-108">När du skapar ett användar konto i administrations centret för Microsoft 365 kan du inte använda det kontot för att skapa en e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="50bb2-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="50bb2-109">Den rekommenderade metoden för att skapa och hantera e-postanvändare i fristående EOP är att använda profilsynkronisering enligt beskrivningen i avsnittet [använda katalog-synkronisering för att hantera e-postanvändare](#use-directory-synchronization-to-manage-mail-users) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="50bb2-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="50bb2-110">För fristående EOP-organisationer med ett fåtal användare kan du lägga till och hantera e-postanvändare i administrations centret för Exchange (UK) eller fristående EOP PowerShell enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="50bb2-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="50bb2-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="50bb2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="50bb2-112">Om du vill öppna administrations centret för Exchange (UK) läser du [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="50bb2-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="50bb2-113">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="50bb2-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="50bb2-114">När du skapar e-postanvändare i EOP PowerShell kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="50bb2-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="50bb2-115">Dessutom använder PowerShell-cmdlets för EOP en grupp bearbetnings metod som resulterar i ett par minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="50bb2-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="50bb2-116">Du måste ha behörighet i Exchange Online Protection innan du kan göra det i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="50bb2-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="50bb2-117">Du behöver bara skapa **e-postmottagare** och **e-postmottagare** (ändra), som har tilldelats roll grupperna **organisations hantering** (globala administratörer) och **mottagar hantering** .</span><span class="sxs-lookup"><span data-stu-id="50bb2-117">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="50bb2-118">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="50bb2-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="50bb2-119">Information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="50bb2-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="50bb2-120">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="50bb2-120">Having problems?</span></span> <span data-ttu-id="50bb2-121">Be om hjälp i Exchange-forumen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="50bb2-122">Gå till [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="50bb2-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="50bb2-123">Använda administrations centret för Exchange för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="50bb2-124">Använda UK för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="50bb2-125">Gå till **mottagare** \> **kontakter** i UK.</span><span class="sxs-lookup"><span data-stu-id="50bb2-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="50bb2-126">Klicka på **ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="50bb2-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="50bb2-127">På sidan **ny e-postanvändare** som öppnas konfigurerar du följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="50bb2-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="50bb2-128">Inställningar som är markerade med <sup>\*</sup> är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="50bb2-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="50bb2-129">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="50bb2-129">**First name**</span></span>

   - <span data-ttu-id="50bb2-130">**Initialer**: personens initialer för mellan namn.</span><span class="sxs-lookup"><span data-stu-id="50bb2-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="50bb2-131">**Efter namn**</span><span class="sxs-lookup"><span data-stu-id="50bb2-131">**Last name**</span></span>

   - <span data-ttu-id="50bb2-132"><sup>\*</sup>**Visnings namn**: den här rutan visar som standard värdena i rutorna för **förnamn**, **initialer** och **efter namn** .</span><span class="sxs-lookup"><span data-stu-id="50bb2-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="50bb2-133">Du kan acceptera det här värdet eller ändra det.</span><span class="sxs-lookup"><span data-stu-id="50bb2-133">You can accept this value or change it.</span></span> <span data-ttu-id="50bb2-134">Värdet ska vara unikt och får innehålla högst 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="50bb2-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="50bb2-135"><sup>\*</sup>**Alias**: Ange ett unikt alias med upp till 64 tecken för användaren</span><span class="sxs-lookup"><span data-stu-id="50bb2-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="50bb2-136">**Extern e-post adress**: Ange användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="50bb2-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="50bb2-137">Domänen bör vara extern för den molnbaserade organisationen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="50bb2-138"><sup>\*</sup>**Användar-ID**: Ange det konto som personen ska använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="50bb2-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="50bb2-139">Användar-ID: t består av ett användar namn på vänster sida av snabel-a (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="50bb2-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="50bb2-140"><sup>\*</sup>**Nytt lösen** ord och <sup>\*</sup> **Bekräfta lösen ord**: Ange och ange lösen ordet för kontot igen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="50bb2-141">Kontrol lera att lösen ordet uppfyller kraven för lösen ord, komplexitet och historik för din organisation.</span><span class="sxs-lookup"><span data-stu-id="50bb2-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="50bb2-142">När du är klar klickar du på **Spara** för att skapa e-postkontot.</span><span class="sxs-lookup"><span data-stu-id="50bb2-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="50bb2-143">Använda UK för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="50bb2-144">Gå till **mottagare** \> **kontakter** i UK.</span><span class="sxs-lookup"><span data-stu-id="50bb2-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="50bb2-145">Markera den e-postanvändare som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="50bb2-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="50bb2-146">På sidan med egenskaper för e-postkonton som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="50bb2-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="50bb2-147">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="50bb2-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="50bb2-148">Allmänt</span><span class="sxs-lookup"><span data-stu-id="50bb2-148">General</span></span>

<span data-ttu-id="50bb2-149">Använd fliken **Allmänt** för att visa eller ändra grundläggande information om e-postkontot.</span><span class="sxs-lookup"><span data-stu-id="50bb2-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="50bb2-150">**Förnamn**</span><span class="sxs-lookup"><span data-stu-id="50bb2-150">**First name**</span></span>

- <span data-ttu-id="50bb2-151">**Initialer**</span><span class="sxs-lookup"><span data-stu-id="50bb2-151">**Initials**</span></span>

- <span data-ttu-id="50bb2-152">**Efter namn**</span><span class="sxs-lookup"><span data-stu-id="50bb2-152">**Last name**</span></span>

- <span data-ttu-id="50bb2-153">**Visnings namn**: det här namnet visas i organisationens adress bok på raderna till: och från: i e-post och i listan med kontakter i UK.</span><span class="sxs-lookup"><span data-stu-id="50bb2-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="50bb2-154">Det här namnet får inte innehålla tomma blank steg före eller efter visnings namnet.</span><span class="sxs-lookup"><span data-stu-id="50bb2-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="50bb2-155">**Användar-ID**: det här är användarens konto i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50bb2-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="50bb2-156">Du kan inte ändra detta värde här.</span><span class="sxs-lookup"><span data-stu-id="50bb2-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="50bb2-157">Kontakt information</span><span class="sxs-lookup"><span data-stu-id="50bb2-157">Contact information</span></span>

<span data-ttu-id="50bb2-158">Använd fliken **kontakt information** för att visa eller ändra användarens kontakt information.</span><span class="sxs-lookup"><span data-stu-id="50bb2-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="50bb2-159">Informationen på den här sidan visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="50bb2-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="50bb2-160">**Gatu**</span><span class="sxs-lookup"><span data-stu-id="50bb2-160">**Street**</span></span>
- <span data-ttu-id="50bb2-161">**Ort**</span><span class="sxs-lookup"><span data-stu-id="50bb2-161">**City**</span></span>
- <span data-ttu-id="50bb2-162">**Delstat/provins**</span><span class="sxs-lookup"><span data-stu-id="50bb2-162">**State/Province**</span></span>
- <span data-ttu-id="50bb2-163">**Postnummer**</span><span class="sxs-lookup"><span data-stu-id="50bb2-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="50bb2-164">**Land/region**</span><span class="sxs-lookup"><span data-stu-id="50bb2-164">**Country/Region**</span></span>
- <span data-ttu-id="50bb2-165">**Telefon, arbete**</span><span class="sxs-lookup"><span data-stu-id="50bb2-165">**Work phone**</span></span>
- <span data-ttu-id="50bb2-166">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="50bb2-166">**Mobile phone**</span></span>
- <span data-ttu-id="50bb2-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="50bb2-167">**Fax**</span></span>
- <span data-ttu-id="50bb2-168">**Fler alternativ**</span><span class="sxs-lookup"><span data-stu-id="50bb2-168">**More options**</span></span>

  - <span data-ttu-id="50bb2-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="50bb2-169">**Office**</span></span>
  - <span data-ttu-id="50bb2-170">**Telefon hem**</span><span class="sxs-lookup"><span data-stu-id="50bb2-170">**Home phone**</span></span>
  - <span data-ttu-id="50bb2-171">**Webbsida**</span><span class="sxs-lookup"><span data-stu-id="50bb2-171">**Web page**</span></span>
  - <span data-ttu-id="50bb2-172">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="50bb2-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="50bb2-173">Organisation</span><span class="sxs-lookup"><span data-stu-id="50bb2-173">Organization</span></span>

<span data-ttu-id="50bb2-174">Använd fliken **organisation** för att registrera detaljerad information om användarens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="50bb2-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="50bb2-175">**Title**</span></span>
- <span data-ttu-id="50bb2-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="50bb2-176">**Department**</span></span>
- <span data-ttu-id="50bb2-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="50bb2-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="50bb2-178">Använda UK för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="50bb2-179">Gå till **mottagare** \> **kontakter** i UK.</span><span class="sxs-lookup"><span data-stu-id="50bb2-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="50bb2-180">Markera den e-postanvändare som du vill ta bort och klicka sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="50bb2-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="50bb2-181">Använda PowerShell för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="50bb2-182">Använda fristående EOP PowerShell för att visa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="50bb2-183">Om du vill returnera en sammanfattnings lista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="50bb2-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="50bb2-184">Om du vill visa detaljerad information om en viss e-postanvändare ersätter du \<MailUserIdentity\> med namn, alias eller konto namn för e-postkontot och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="50bb2-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="50bb2-185">Detaljerad information om syntax och parametrar finns i [Hämta-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [få-användare](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="50bb2-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="50bb2-186">Använda fristående EOP PowerShell för att skapa e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="50bb2-187">Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="50bb2-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="50bb2-188">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="50bb2-188">**Notes**:</span></span>

- <span data-ttu-id="50bb2-189">Parametern _namn_ är obligatorisk, har en maximal längd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="50bb2-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="50bb2-190">Om du inte använder parametern _DisplayName_ används värdet för _namn_ parametern som visnings namn.</span><span class="sxs-lookup"><span data-stu-id="50bb2-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="50bb2-191">Om du inte använder _Ali Aset_ används den vänstra sidan av parametern _MicrosoftOnlineServicesID_ för aliaset.</span><span class="sxs-lookup"><span data-stu-id="50bb2-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="50bb2-192">Om du inte använder parametern _ExternalEmailAddress_ används värdet _MicrosoftOnlineServicesID_ för den externa e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="50bb2-193">I det här exemplet skapas en e-postanvändare med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="50bb2-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="50bb2-194">Namnet är JeffreyZeng och visnings namnet är Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="50bb2-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="50bb2-195">Förnamnet är Jeffrey och efter namnet är Zeng.</span><span class="sxs-lookup"><span data-stu-id="50bb2-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="50bb2-196">Aliaset är jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="50bb2-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="50bb2-197">Den externa e-postadressen är jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="50bb2-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="50bb2-198">Konto namnet är jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="50bb2-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="50bb2-199">Lösen ordet är pa $ $word 1.</span><span class="sxs-lookup"><span data-stu-id="50bb2-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="50bb2-200">Detaljerad information om syntax och parametrar finns i [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="50bb2-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="50bb2-201">Använda fristående EOP PowerShell för att ändra e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="50bb2-202">Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="50bb2-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="50bb2-203">I det här exemplet anges den externa e-postadressen för pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="50bb2-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="50bb2-204">I det här exemplet anges företags egenskapen för alla e-postanvändare till contoso.</span><span class="sxs-lookup"><span data-stu-id="50bb2-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="50bb2-205">Detaljerad information om syntax och parametrar finns i [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="50bb2-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="50bb2-206">Använda fristående EOP PowerShell för att ta bort e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="50bb2-207">Om du vill ta bort e-postkonton i fristående EOP PowerShell ersätter du \<MailUserIdentity\> med namn, alias eller konto namn för e-postanvändaren och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="50bb2-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="50bb2-208">Det här exemplet tar bort e-postkontot för Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="50bb2-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="50bb2-209">Detaljerad information om syntax och parametrar finns i [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="50bb2-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="50bb2-210">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="50bb2-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="50bb2-211">Så här kontrollerar du att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP:</span><span class="sxs-lookup"><span data-stu-id="50bb2-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="50bb2-212">Gå till **mottagare** \> **kontakter** i UK.</span><span class="sxs-lookup"><span data-stu-id="50bb2-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="50bb2-213">Kontrol lera att e-postmeddelandet finns med i listan (eller inte listat).</span><span class="sxs-lookup"><span data-stu-id="50bb2-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="50bb2-214">Markera e-postkontot och Visa informationen i informations fönstret eller klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) för att visa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="50bb2-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="50bb2-215">I fristående EOP PowerShell kör du följande kommando för att kontrol lera att e-postmeddelandet är listad (eller inte listad):</span><span class="sxs-lookup"><span data-stu-id="50bb2-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="50bb2-216">Ersätt \<MailUserIdentity\> med namn, alias eller konto namn för e-postkontot och kör följande kommandon för att kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="50bb2-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="50bb2-217">Använda Katalogduplicering för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="50bb2-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="50bb2-218">I fristående EOP är Directory-synkronisering tillgängligt för kunder med lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50bb2-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="50bb2-219">Du kan synkronisera dessa konton med Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="50bb2-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="50bb2-220">När du synkroniserar dina befintliga användar konton till Azure Active Directory kan du visa dessa användare i fönstret **mottagare** i administrations centret för Exchange (UK) eller i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50bb2-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="50bb2-221">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="50bb2-221">**Notes**:</span></span>

- <span data-ttu-id="50bb2-222">Om du använder katalog synkronisering för att hantera mottagarna kan du ändå lägga till och hantera användare i administrations centret för Microsoft 365, men de kommer inte att synkroniseras med din lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50bb2-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="50bb2-223">Detta beror på att Active Directory-synkroniseringen bara synkroniserar mottagare från din lokala aktiva katalog till molnet.</span><span class="sxs-lookup"><span data-stu-id="50bb2-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="50bb2-224">Du rekommenderas att använda profilsynkronisering med följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="50bb2-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="50bb2-225">Listorna **Betrodda avsändare och spärrade avsändare i Outlook**: när du synkroniserar till tjänsten får de här listorna högre prioritet än skräp post filtrering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="50bb2-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="50bb2-226">Då kan användarna hantera sin egen lista över betrodda avsändare och spärrade avsändare med enskilda avsändare och domän poster.</span><span class="sxs-lookup"><span data-stu-id="50bb2-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="50bb2-227">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="50bb2-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="50bb2-228">**Mappbaserade Edge-blockering (DBEB)**: Mer information om DBEB finns i [använda katalogbaserade Edge-blockering för att neka meddelanden skickade till ogiltiga mottagare](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="50bb2-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="50bb2-229">**Slutanvändare åtkomst till karantän**: för att få åtkomst till deras karantän meddelanden måste mottagarna ha ett giltigt användar-ID och lösen ord i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="50bb2-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="50bb2-230">Mer information om karantän finns i [hitta och släppa meddelanden i karantän som en användare](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50bb2-230">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="50bb2-231">**Regler för e-postflöde (kallas även transport regler)**: när du använder katalog synkronisering laddas de befintliga Active Directory-användarna och-grupperna automatiskt till molnet, och du kan skapa regler för e-postflöde som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="50bb2-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="50bb2-232">Observera att [dynamiska distributions grupper](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras med katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="50bb2-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="50bb2-233">Skaffa nödvändiga behörigheter och förbereda för Active Directory-synkronisering enligt beskrivningen i [Vad är hybrid identitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="50bb2-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="50bb2-234">Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="50bb2-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="50bb2-235">Aktivera katalog synkronisering enligt beskrivningen i [Azure AD Connect-synkronisering: förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="50bb2-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="50bb2-236">Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen i [förutsättningar för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="50bb2-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="50bb2-237">[Välj vilken Installations typ som ska användas för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="50bb2-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="50bb2-238">Express</span><span class="sxs-lookup"><span data-stu-id="50bb2-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="50bb2-239">Företagsanpassade</span><span class="sxs-lookup"><span data-stu-id="50bb2-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="50bb2-240">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="50bb2-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="50bb2-241">När du är klar med konfigurations guiden för Azure Active Directory-Synkroniseringshanteraren skapas **MSOL_AD_Sync** -kontot i Active Directory-skogen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="50bb2-242">Det här kontot används för att läsa och synkronisera din lokala Active Directory-information.</span><span class="sxs-lookup"><span data-stu-id="50bb2-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="50bb2-243">För att Active Directory-synkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogpartitionen är öppen.</span><span class="sxs-lookup"><span data-stu-id="50bb2-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="50bb2-244">När du har konfigurerat din synkronisering måste du kontrol lera att AAD Connect är synkroniserat korrekt.</span><span class="sxs-lookup"><span data-stu-id="50bb2-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="50bb2-245">I UK går du till **mottagare** - \> **kontakter** och visar att listan över användare har synkroniserats korrekt från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="50bb2-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
