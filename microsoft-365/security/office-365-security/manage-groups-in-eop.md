---
title: Hantera grupper i EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratörer i fristående EOP-organisationer (Exchange Online Protection) kan lära sig hur du skapar, ändrar och tar bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i Exchange-administrationscentret (EAC) och i fristående EOP-powershell (Exchange Online Protection).
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209025"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="332a1-103">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="332a1-103">Manage groups in EOP</span></span>

<span data-ttu-id="332a1-104">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:</span><span class="sxs-lookup"><span data-stu-id="332a1-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="332a1-105">**Distributionsgrupper**: En samling e-postanvändare eller andra distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="332a1-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="332a1-106">Till exempel team eller andra ad hoc-grupper som behöver ta emot eller skicka e-post inom ett gemensamt intresseområde.</span><span class="sxs-lookup"><span data-stu-id="332a1-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="332a1-107">Distributionsgrupper är uteslutande avsedda för distribution av e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha behörigheter tilldelade till dem).</span><span class="sxs-lookup"><span data-stu-id="332a1-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="332a1-108">**E-postaktiverade säkerhetsgrupper**: En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörigheter för administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="332a1-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="332a1-109">Du kanske till exempel vill ge specifika användaradministratörsbehörigheter så att de kan konfigurera inställningar för skräppost och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="332a1-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="332a1-110">Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa (oautentiserade) avsändare.</span><span class="sxs-lookup"><span data-stu-id="332a1-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="332a1-111">Lägg inte till distributionsgrupper i e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="332a1-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="332a1-112">.</span><span class="sxs-lookup"><span data-stu-id="332a1-112">.</span></span>

<span data-ttu-id="332a1-113">Du kan hantera grupper i Administrationscenter för Exchange (EAC) och i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="332a1-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="332a1-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="332a1-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="332a1-115">Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="332a1-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="332a1-116">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="332a1-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="332a1-117">När du hanterar grupper i fristående EOP PowerShell kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="332a1-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="332a1-118">PowerShell-procedurerna i det här avsnittet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="332a1-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="332a1-119">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="332a1-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="332a1-120">Du behöver rollen Distributionsgrupper, som tilldelas rollgrupperna OrganizationManagement (global admins) och RecipientManagement som standard.</span><span class="sxs-lookup"><span data-stu-id="332a1-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="332a1-121">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="332a1-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="332a1-122">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="332a1-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="332a1-123">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="332a1-123">Having problems?</span></span> <span data-ttu-id="332a1-124">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="332a1-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="332a1-125">Använda administrationscentret för Exchange för att hantera distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="332a1-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="332a1-126">Använd EAC för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="332a1-127">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="332a1-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="332a1-128">Klicka på **Ny** ![ ny ikon och välj sedan något av ](../../media/ITPro-EAC-AddIcon.png) följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="332a1-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="332a1-129">**Distributionsgrupp**</span><span class="sxs-lookup"><span data-stu-id="332a1-129">**Distribution group**</span></span>

   - <span data-ttu-id="332a1-130">**E-postaktiverad säkerhetsgrupp**</span><span class="sxs-lookup"><span data-stu-id="332a1-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="332a1-131">Konfigurera följande inställningar på den nya gruppsidan som öppnas.</span><span class="sxs-lookup"><span data-stu-id="332a1-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="332a1-132">Inställningar markerade med en <sup>\*</sup> krävs.</span><span class="sxs-lookup"><span data-stu-id="332a1-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="332a1-133"><sup>\*</sup>**Visningsnamn**: Det här namnet visas i organisationens adressbok, på raden Till: när e-post skickas till den här gruppen och i listan **Grupper** i EAC.</span><span class="sxs-lookup"><span data-stu-id="332a1-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="332a1-134">Visningsnamnet krävs, måste vara unikt och ska vara användarvänligt så att folk känner igen vad det är.</span><span class="sxs-lookup"><span data-stu-id="332a1-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="332a1-135"><sup>\*</sup>**Alias**: Använd den här rutan om du vill skriva namnet på aliaset för gruppen.</span><span class="sxs-lookup"><span data-stu-id="332a1-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="332a1-136">Aliaset får inte vara längre än 64 tecken och måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="332a1-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="332a1-137">När en användare skriver aliaset på raden Till i ett e-postmeddelande matchas det till gruppens visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="332a1-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="332a1-138"><sup>\*</sup>**E-postadress:** E-postadressen består av aliaset till vänster om at-symbolen (@) och en domän till höger.</span><span class="sxs-lookup"><span data-stu-id="332a1-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="332a1-139">Som standard används värdet **för Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="332a1-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="332a1-140">För domänvärdet klickar du på listrutan och väljer och accepterar domänen i organisationen.</span><span class="sxs-lookup"><span data-stu-id="332a1-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="332a1-141">**Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="332a1-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="332a1-142"><sup>\*</sup>**Ägare**: En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="332a1-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="332a1-143">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="332a1-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="332a1-144">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="332a1-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="332a1-145">Om du vill lägga till ägare klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="332a1-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="332a1-146">Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="332a1-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="332a1-147">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="332a1-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="332a1-148">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="332a1-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="332a1-149">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="332a1-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="332a1-150">**Medlemmar**: Lägg till och ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="332a1-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="332a1-151">Om du vill lägga till medlemmar klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="332a1-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="332a1-152">Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="332a1-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="332a1-153">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="332a1-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="332a1-154">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="332a1-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="332a1-155">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="332a1-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="332a1-156">När du är klar klickar du på **Spara** för att skapa distributionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="332a1-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="332a1-157">Använda EAC för att ändra distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="332a1-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="332a1-158">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="332a1-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="332a1-159">Markera den distributionsgrupp eller den e-postaktiverade säkerhetsgrupp som du vill ändra i listan med grupper och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-AddIcon.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="332a1-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="332a1-160">På sidan egenskaper för distributionsgrupp som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="332a1-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="332a1-161">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="332a1-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="332a1-162">Allmänt</span><span class="sxs-lookup"><span data-stu-id="332a1-162">General</span></span>

<span data-ttu-id="332a1-163">Använd den här fliken om du vill visa eller ändra grundläggande information om gruppen.</span><span class="sxs-lookup"><span data-stu-id="332a1-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="332a1-164">**Visningsnamn**: Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper**.</span><span class="sxs-lookup"><span data-stu-id="332a1-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="332a1-165">Visningsnamnet krävs och bör vara användarvänligt så att folk känner igen vad det är.</span><span class="sxs-lookup"><span data-stu-id="332a1-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="332a1-166">Det måste också vara unikt i din domän.</span><span class="sxs-lookup"><span data-stu-id="332a1-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="332a1-167">Om du har implementerat en gruppnamnprincip måste visningsnamnet överensstämma med det namngivningsformat som definieras av principen.</span><span class="sxs-lookup"><span data-stu-id="332a1-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="332a1-168">**Alias**: Det här är den del av e-postadressen som visas till vänster om at-symbolen (@).</span><span class="sxs-lookup"><span data-stu-id="332a1-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="332a1-169">Om du ändrar aliaset ändras även den primära SMTP-adressen för gruppen och det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="332a1-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="332a1-170">Dessutom kommer e-postadressen med det tidigare aliaset att behållas som en proxyadress för gruppen.</span><span class="sxs-lookup"><span data-stu-id="332a1-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="332a1-171">**E-postadress:** E-postadressen består av aliaset till vänster om at-symbolen (@) och en domän till höger.</span><span class="sxs-lookup"><span data-stu-id="332a1-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="332a1-172">Som standard används värdet **för Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="332a1-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="332a1-173">För domänvärdet klickar du på listrutan och väljer och accepterar domänen i organisationen.</span><span class="sxs-lookup"><span data-stu-id="332a1-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="332a1-174">**Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="332a1-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="332a1-175">Ägande</span><span class="sxs-lookup"><span data-stu-id="332a1-175">Ownership</span></span>

<span data-ttu-id="332a1-176">Använd den här fliken om du vill tilldela gruppägare.</span><span class="sxs-lookup"><span data-stu-id="332a1-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="332a1-177">En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="332a1-177">A group owner can manage group membership.</span></span> <span data-ttu-id="332a1-178">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="332a1-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="332a1-179">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="332a1-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="332a1-180">Om du vill lägga till ägare klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="332a1-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="332a1-181">Leta reda på och markera en mottagare i dialogrutan som visas och klicka sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="332a1-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="332a1-182">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="332a1-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="332a1-183">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="332a1-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="332a1-184">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="332a1-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="332a1-185">Medlemskap</span><span class="sxs-lookup"><span data-stu-id="332a1-185">Membership</span></span>

<span data-ttu-id="332a1-186">Använd den här fliken om du vill lägga till eller ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="332a1-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="332a1-187">Gruppägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="332a1-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="332a1-188">Om du vill lägga till medlemmar klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="332a1-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="332a1-189">Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="332a1-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="332a1-190">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="332a1-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="332a1-191">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="332a1-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="332a1-192">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="332a1-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="332a1-193">Använd EAC för att ta bort grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="332a1-194">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="332a1-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="332a1-195">Markera den distributionsgrupp som du vill ta bort i listan med grupper och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="332a1-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="332a1-196">Använda PowerShell för att hantera grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="332a1-197">Använda fristående EOP PowerShell för att visa grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="332a1-198">Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="332a1-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="332a1-199">Om du vill returnera listan över gruppmedlemmar ersätter du \< GroupIdentity \> med gruppens namn, alias eller e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="332a1-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="332a1-200">Detaljerad syntax- och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) och [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="332a1-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="332a1-201">Använda fristående EOP PowerShell för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="332a1-202">Om du vill skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="332a1-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="332a1-203">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="332a1-203">**Notes**:</span></span>

- <span data-ttu-id="332a1-204">Parametern _Name_ krävs, har en maximal längd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="332a1-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="332a1-205">Om du inte använder parametern _DisplayName_ används värdet för parametern _Name_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="332a1-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="332a1-206">Om du inte använder parametern _Alias_ används parametern _Name_ för aliasvärdet.</span><span class="sxs-lookup"><span data-stu-id="332a1-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="332a1-207">Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).</span><span class="sxs-lookup"><span data-stu-id="332a1-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="332a1-208">Om du inte använder parametern _PrimarySmtpAddress_ används aliasvärdet i parametern _PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="332a1-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="332a1-209">Om du inte använder parametern _Typ_ är standardvärdet Distribution.</span><span class="sxs-lookup"><span data-stu-id="332a1-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="332a1-210">I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="332a1-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="332a1-211">Detaljerad syntax- och parameterinformation finns i [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="332a1-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="332a1-212">Använda fristående EOP PowerShell för att ändra grupper</span><span class="sxs-lookup"><span data-stu-id="332a1-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="332a1-213">Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="332a1-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="332a1-214">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle-anställda för att sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="332a1-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="332a1-215">Det här exemplet ersätter de nuvarande medlemmarna i gruppen Säkerhetsteam med Kitty Petersen och Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="332a1-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="332a1-216">I det här exemplet läggs en ny användare till Tyson Fawcett i gruppen Security Team samtidigt som de aktuella medlemmarna i gruppen bevaras.</span><span class="sxs-lookup"><span data-stu-id="332a1-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="332a1-217">Detaljerad syntax- och parameterinformation finns i [Ange-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="332a1-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="332a1-218">Ta bort en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="332a1-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="332a1-219">I det här exemplet tas distributionsgruppen IT-administratörer bort.</span><span class="sxs-lookup"><span data-stu-id="332a1-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="332a1-220">Detaljerad syntax- och parameterinformation finns i [Ta bort EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="332a1-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="332a1-221">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="332a1-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="332a1-222">Så här kontrollerar du att du har skapat, ändrat eller tagit bort en distributionsgrupp eller en e-postaktiverad säkerhetsgrupp:</span><span class="sxs-lookup"><span data-stu-id="332a1-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="332a1-223">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="332a1-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="332a1-224">Kontrollera att gruppen visas (eller inte visas) och kontrollera värdet **för grupptypen.**</span><span class="sxs-lookup"><span data-stu-id="332a1-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="332a1-225">Markera gruppen och visa informationen i informationsfönstret eller klicka på **Ikonen Redigera** ![ redigera för att visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="332a1-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="332a1-226">I fristående EOP PowerShell kör du följande kommando för att kontrollera att gruppen visas (eller inte finns med i listan):</span><span class="sxs-lookup"><span data-stu-id="332a1-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="332a1-227">Ersätt \< GroupIdentity \> med gruppens namn, alias eller e-postadress och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="332a1-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="332a1-228">Om du vill visa gruppmedlemmarna ersätter du \< GroupIdentity \> med gruppens namn, alias eller e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="332a1-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
