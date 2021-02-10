---
title: Hantera grupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratörer i fristående Exchange Online Protection-organisationer (EOP) kan lära sig att skapa, ändra och ta bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange (EAC) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166969"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="43cab-103">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="43cab-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="43cab-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="43cab-104">**Applies to**</span></span>
-  [<span data-ttu-id="43cab-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="43cab-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="43cab-106">I fristående Exchange Online Protection -organisationer (EOP) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:</span><span class="sxs-lookup"><span data-stu-id="43cab-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="43cab-107">**Distributionsgrupper:** En samling e-postanvändare eller andra distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="43cab-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="43cab-108">Till exempel grupper eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse.</span><span class="sxs-lookup"><span data-stu-id="43cab-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="43cab-109">Distributionsgrupper är enbart för distribution av e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha tilldelats behörighet).</span><span class="sxs-lookup"><span data-stu-id="43cab-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="43cab-110">**E-postaktiverade säkerhetsgrupper:** En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörighet för administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="43cab-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="43cab-111">Du kanske till exempel vill ge vissa grupper av användare administratörsbehörigheter så att de kan konfigurera inställningarna för skydd mot skräppost och skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="43cab-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="43cab-112">Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa (oauticerade) avsändare.</span><span class="sxs-lookup"><span data-stu-id="43cab-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="43cab-113">Lägg inte till distributionsgrupper i e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="43cab-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="43cab-114">Du kan hantera grupper i administrationscentret för Exchange (EAC) och i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43cab-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="43cab-115">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="43cab-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="43cab-116">Information om hur du öppnar administrationscentret för Exchange finns [i administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="43cab-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="43cab-117">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="43cab-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="43cab-118">När du hanterar grupper i fristående EOP PowerShell kan det uppstå begränsningar.</span><span class="sxs-lookup"><span data-stu-id="43cab-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="43cab-119">PowerShell-procedurerna i den här artikeln använder en batchbearbetningsmetod som resulterar i en överföringsfördröjning på några minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="43cab-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="43cab-120">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="43cab-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="43cab-121">Specifikt behöver du rollen **Distributionsgrupper,** som är tilldelad **rollgrupperna Organisationshantering** **och Mottagarhantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="43cab-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="43cab-122">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="43cab-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="43cab-123">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="43cab-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="43cab-124">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="43cab-124">Having problems?</span></span> <span data-ttu-id="43cab-125">Be om hjälp i [forumet för Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="43cab-125">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="43cab-126">Använda administrationscentret för Exchange för att hantera distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="43cab-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="43cab-127">Använda EAC för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="43cab-128">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="43cab-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="43cab-129">Klicka **på** ![ ikonen Nytt nytt och välj sedan något av följande ](../../media/ITPro-EAC-AddIcon.png) alternativ:</span><span class="sxs-lookup"><span data-stu-id="43cab-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="43cab-130">**Distributionsgrupp**</span><span class="sxs-lookup"><span data-stu-id="43cab-130">**Distribution group**</span></span>

   - <span data-ttu-id="43cab-131">**E-postaktiverad säkerhetsgrupp**</span><span class="sxs-lookup"><span data-stu-id="43cab-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="43cab-132">På den nya gruppsidan som öppnas konfigurerar du följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="43cab-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="43cab-133">Inställningar som är markerade med <sup>\*</sup> ett måste.</span><span class="sxs-lookup"><span data-stu-id="43cab-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="43cab-134"><sup>\*</sup>**Visningsnamn:** Det här namnet visas i organisationens adressbok, på raden Till: när  e-post skickas till den här gruppen och i listan Grupper i EAC.</span><span class="sxs-lookup"><span data-stu-id="43cab-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="43cab-135">Visningsnamnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att andra känner igen det.</span><span class="sxs-lookup"><span data-stu-id="43cab-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="43cab-136"><sup>\*</sup>**Alias:** Skriv namnet på gruppens alias i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="43cab-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="43cab-137">Alias får inte vara längre än 64 tecken och måste vara unika.</span><span class="sxs-lookup"><span data-stu-id="43cab-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="43cab-138">När en användare skriver alias på raden Till i ett e-postmeddelande matchas det med gruppens visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="43cab-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="43cab-139"><sup>\*</sup>**E-postadress:** E-postadressen består av alias till vänster om at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="43cab-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="43cab-140">Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="43cab-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="43cab-141">För domänvärdet klickar du på listrutan och väljer och godkänner domänen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="43cab-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="43cab-142">**Beskrivning:** Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="43cab-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="43cab-143"><sup>\*</sup>**Ägare:** En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="43cab-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="43cab-144">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="43cab-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="43cab-145">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="43cab-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="43cab-146">Om du vill lägga till ägare klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till.</span><span class="sxs-lookup"><span data-stu-id="43cab-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="43cab-147">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.**</span><span class="sxs-lookup"><span data-stu-id="43cab-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="43cab-148">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="43cab-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="43cab-149">Klicka på OK när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="43cab-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="43cab-150">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ikonen Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="43cab-151">**Medlemmar:** Lägg till och ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="43cab-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="43cab-152">Om du vill lägga till medlemmar klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till.</span><span class="sxs-lookup"><span data-stu-id="43cab-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="43cab-153">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.**</span><span class="sxs-lookup"><span data-stu-id="43cab-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="43cab-154">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="43cab-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="43cab-155">Klicka på OK när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="43cab-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="43cab-156">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="43cab-157">När du är klar klickar du på **Spara** för att skapa distributionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="43cab-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="43cab-158">Använda EAC för att ändra distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="43cab-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="43cab-159">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="43cab-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="43cab-160">I listan över grupper väljer du den distributionsgrupp eller e-postaktiverade  säkerhetsgrupp som du vill ändra och klickar sedan på ![ redigeringsikonen. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="43cab-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="43cab-161">Klicka på någon av följande flikar på sidan med egenskaper för distributionsgruppen som öppnas om du vill visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="43cab-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="43cab-162">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="43cab-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="43cab-163">Allmänt</span><span class="sxs-lookup"><span data-stu-id="43cab-163">General</span></span>

<span data-ttu-id="43cab-164">Använd den här fliken för att visa eller ändra grundläggande information om gruppen.</span><span class="sxs-lookup"><span data-stu-id="43cab-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="43cab-165">**Visningsnamn:** Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper.**</span><span class="sxs-lookup"><span data-stu-id="43cab-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="43cab-166">Visningsnamnet är obligatoriskt och bör vara användarvänligt så att det är lätt att känna igen.</span><span class="sxs-lookup"><span data-stu-id="43cab-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="43cab-167">Den måste också vara unik i din domän.</span><span class="sxs-lookup"><span data-stu-id="43cab-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="43cab-168">Om du har implementerat en gruppnamnsprincip måste visningsnamnet följa namnformatet som definieras av principen.</span><span class="sxs-lookup"><span data-stu-id="43cab-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="43cab-169">**Alias:** Det här är den del av e-postadressen som visas till vänster om at-symbolen (@).</span><span class="sxs-lookup"><span data-stu-id="43cab-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="43cab-170">Om du ändrar alias ändras även gruppens primära SMTP-adress och innehåller det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="43cab-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="43cab-171">Dessutom sparas e-postadressen med det tidigare aliaset som proxyadress för gruppen.</span><span class="sxs-lookup"><span data-stu-id="43cab-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="43cab-172">**E-postadress:** E-postadressen består av alias till vänster om at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="43cab-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="43cab-173">Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="43cab-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="43cab-174">För domänvärdet klickar du på listrutan och väljer och godkänner domänen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="43cab-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="43cab-175">**Beskrivning:** Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="43cab-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="43cab-176">Ägarskap</span><span class="sxs-lookup"><span data-stu-id="43cab-176">Ownership</span></span>

<span data-ttu-id="43cab-177">Använd den här fliken för att tilldela gruppägare.</span><span class="sxs-lookup"><span data-stu-id="43cab-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="43cab-178">En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="43cab-178">A group owner can manage group membership.</span></span> <span data-ttu-id="43cab-179">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="43cab-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="43cab-180">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="43cab-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="43cab-181">Om du vill lägga till ägare klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till.</span><span class="sxs-lookup"><span data-stu-id="43cab-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="43cab-182">I dialogrutan som visas går du till och väljer en mottagare och klickar sedan **på lägg till ->.**</span><span class="sxs-lookup"><span data-stu-id="43cab-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="43cab-183">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="43cab-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="43cab-184">Klicka på OK när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="43cab-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="43cab-185">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ikonen Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="43cab-186">Medlemskap</span><span class="sxs-lookup"><span data-stu-id="43cab-186">Membership</span></span>

<span data-ttu-id="43cab-187">Använd den här fliken för att lägga till eller ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="43cab-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="43cab-188">Gruppägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="43cab-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="43cab-189">Om du vill lägga till medlemmar klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till.</span><span class="sxs-lookup"><span data-stu-id="43cab-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="43cab-190">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.**</span><span class="sxs-lookup"><span data-stu-id="43cab-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="43cab-191">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="43cab-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="43cab-192">Klicka på OK när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="43cab-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="43cab-193">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="43cab-194">Använda EAC för att ta bort grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="43cab-195">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="43cab-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="43cab-196">Markera den distributionsgrupp som du vill ta bort i listan med grupper och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="43cab-197">Använda PowerShell för att hantera grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="43cab-198">Använda fristående EOP PowerShell för att visa grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="43cab-199">Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="43cab-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="43cab-200">Om du vill returnera listan över gruppmedlemmar ersätter du med gruppens namn, alias eller e-postadress \<GroupIdentity\> och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="43cab-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="43cab-201">Detaljerad information om syntax och parametrar finns i [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="43cab-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="43cab-202">Använda fristående EOP PowerShell för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="43cab-203">Använd följande syntax för att skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="43cab-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="43cab-204">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="43cab-204">**Notes**:</span></span>

- <span data-ttu-id="43cab-205">_Namnparametern_ är obligatorisk, får innehålla högst 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="43cab-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="43cab-206">Om du inte använder _displayName-parametern_ används värdet för _namnparametern_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="43cab-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="43cab-207">Om du inte använder _aliasparametern_ _används namnparametern_ för aliasvärdet.</span><span class="sxs-lookup"><span data-stu-id="43cab-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="43cab-208">Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).</span><span class="sxs-lookup"><span data-stu-id="43cab-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="43cab-209">Om du inte använder _parametern PrimarySmtpAddress_ används aliasvärdet i _parametern PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="43cab-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="43cab-210">Om du inte använder _parametern Typ_ är standardvärdet Fördelning.</span><span class="sxs-lookup"><span data-stu-id="43cab-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="43cab-211">I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="43cab-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="43cab-212">Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="43cab-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="43cab-213">Använda fristående EOP PowerShell för att ändra grupper</span><span class="sxs-lookup"><span data-stu-id="43cab-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="43cab-214">Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="43cab-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="43cab-215">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Anställda i Seattle till sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="43cab-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="43cab-216">Det här exemplet ersätter de aktuella medlemmarna i gruppen Säkerhetsgrupp med Peter Petersen och Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="43cab-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="43cab-217">I det här exemplet läggs en ny användare med namnet Tyson Fawcett till i gruppen Säkerhetsgrupp, samtidigt som de aktuella medlemmarna i gruppen bevaras.</span><span class="sxs-lookup"><span data-stu-id="43cab-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="43cab-218">Detaljerad information om syntax och parametrar finns [i Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="43cab-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="43cab-219">Ta bort en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43cab-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="43cab-220">I det här exemplet tas distributionsgruppen MED namnet IT-administratörer bort.</span><span class="sxs-lookup"><span data-stu-id="43cab-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="43cab-221">Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="43cab-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="43cab-222">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="43cab-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="43cab-223">Kontrollera att du har skapat, ändrat eller tagit bort en distributionsgrupp eller e-postaktiverad säkerhetsgrupp genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="43cab-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="43cab-224">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="43cab-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="43cab-225">Kontrollera att gruppen finns med i listan (eller inte visas) och verifiera **värdet grupptyp.**</span><span class="sxs-lookup"><span data-stu-id="43cab-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="43cab-226">Markera gruppen och visa informationen i informationsfönstret, eller klicka på **redigeringsikonen** ![ för att visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="43cab-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="43cab-227">Kör följande kommando i fristående EOP PowerShell för att verifiera att gruppen listas (eller inte visas):</span><span class="sxs-lookup"><span data-stu-id="43cab-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="43cab-228">Ersätt \<GroupIdentity\> med namn, alias eller e-postadress för gruppen och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="43cab-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="43cab-229">Om du vill visa gruppmedlemmarna ersätter du med gruppens namn, alias eller \<GroupIdentity\> e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="43cab-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
