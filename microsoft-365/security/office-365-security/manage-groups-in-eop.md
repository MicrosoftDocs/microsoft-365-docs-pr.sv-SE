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
description: Administratörer i fristående EOP-organisationer (Exchange Online Protection) kan lära sig att skapa, ändra och ta bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange (EAC) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207023"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="668d0-103">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="668d0-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="668d0-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="668d0-104">**Applies to**</span></span>
-  [<span data-ttu-id="668d0-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="668d0-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="668d0-106">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:</span><span class="sxs-lookup"><span data-stu-id="668d0-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="668d0-107">**Distributionsgrupper:** En samling e-postanvändare eller andra distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="668d0-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="668d0-108">Det kan till exempel vara team eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse.</span><span class="sxs-lookup"><span data-stu-id="668d0-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="668d0-109">Distributionsgrupper är uteslutande för att distribuera e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha tilldelats behörigheter).</span><span class="sxs-lookup"><span data-stu-id="668d0-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="668d0-110">**E-postaktiverade säkerhetsgrupper**: En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörighet för administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="668d0-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="668d0-111">Du kanske till exempel vill ge vissa grupper av användare administratörsbehörigheter så att de kan konfigurera inställningar för skydd mot skräppost och skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="668d0-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="668d0-112">Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa avsändare (oautherade).</span><span class="sxs-lookup"><span data-stu-id="668d0-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="668d0-113">Lägg inte till distributionsgrupper till e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="668d0-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="668d0-114">Du kan hantera grupper i administrationscentret för Exchange (EAC) och i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="668d0-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="668d0-115">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="668d0-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="668d0-116">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="668d0-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="668d0-117">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="668d0-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="668d0-118">När du hanterar grupper i fristående EOP PowerShell kan det uppstå begränsningar.</span><span class="sxs-lookup"><span data-stu-id="668d0-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="668d0-119">PowerShell-procedurerna i den här artikeln använder en batchbearbetningsmetod som resulterar i en överföringsfördröjning på några minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="668d0-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="668d0-120">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="668d0-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="668d0-121">Specifikt behöver du rollen **Distributionsgrupper,** som är tilldelad **rollgrupperna Organisationshantering** och **Mottagarhantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="668d0-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="668d0-122">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="668d0-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="668d0-123">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="668d0-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="668d0-124">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="668d0-124">Having problems?</span></span> <span data-ttu-id="668d0-125">Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="668d0-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="668d0-126">Använda Exchange admin center för att hantera distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="668d0-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="668d0-127">Använda EAC för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="668d0-128">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="668d0-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="668d0-129">Klicka **på** ![ Ny ny ikon och välj sedan något av följande ](../../media/ITPro-EAC-AddIcon.png) alternativ:</span><span class="sxs-lookup"><span data-stu-id="668d0-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="668d0-130">**Distributionsgrupp**</span><span class="sxs-lookup"><span data-stu-id="668d0-130">**Distribution group**</span></span>

   - <span data-ttu-id="668d0-131">**E-postaktiverad säkerhetsgrupp**</span><span class="sxs-lookup"><span data-stu-id="668d0-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="668d0-132">På den nya gruppsidan som öppnas konfigurerar du följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="668d0-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="668d0-133">Inställningar som är markerade med <sup>\*</sup> ett är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="668d0-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="668d0-134"><sup>\*</sup>**Visningsnamn:** Det här namnet visas i organisationens adressbok, på raden Till: när  e-post skickas till den här gruppen och i listan Grupper i EAC.</span><span class="sxs-lookup"><span data-stu-id="668d0-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="668d0-135">Visningsnamnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att det är lätt att känna igen.</span><span class="sxs-lookup"><span data-stu-id="668d0-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="668d0-136"><sup>\*</sup>**Alias**: Använd den här rutan för att skriva namnet på gruppens alias.</span><span class="sxs-lookup"><span data-stu-id="668d0-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="668d0-137">Aliaset får högst innehålla 64 tecken och måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="668d0-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="668d0-138">När en användare skriver alias på raden Till i ett e-postmeddelande matchas det med gruppens visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="668d0-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="668d0-139"><sup>\*</sup>**E-postadress:** E-postadressen består av alias på vänster sida av at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="668d0-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="668d0-140">Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="668d0-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="668d0-141">För domänvärdet klickar du på listrutan och väljer och accepterar domänen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="668d0-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="668d0-142">**Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="668d0-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="668d0-143"><sup>\*</sup>**Ägare**: En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="668d0-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="668d0-144">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="668d0-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="668d0-145">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="668d0-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="668d0-146">Om du vill lägga till ägare klickar du **på Lägg till** lägg ![ till-ikon. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="668d0-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="668d0-147">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="668d0-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="668d0-148">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="668d0-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668d0-149">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="668d0-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="668d0-150">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="668d0-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="668d0-151">**Medlemmar**: Lägga till och ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="668d0-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="668d0-152">Om du vill lägga till medlemmar klickar du **på Lägg till** lägg ![ till-ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="668d0-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="668d0-153">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="668d0-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="668d0-154">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="668d0-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668d0-155">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="668d0-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="668d0-156">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="668d0-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="668d0-157">När du är klar klickar du på **Spara** för att skapa distributionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="668d0-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="668d0-158">Använda EAC för att ändra distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="668d0-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="668d0-159">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="668d0-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="668d0-160">I listan över grupper markerar du den distributionsgrupp eller e-postaktiverade säkerhetsgrupp som du vill ändra och klickar sedan på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="668d0-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="668d0-161">På sidan med egenskaper för distributionsgruppen som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="668d0-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="668d0-162">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="668d0-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="668d0-163">Allmänt</span><span class="sxs-lookup"><span data-stu-id="668d0-163">General</span></span>

<span data-ttu-id="668d0-164">Använd den här fliken för att visa eller ändra grundläggande information om gruppen.</span><span class="sxs-lookup"><span data-stu-id="668d0-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="668d0-165">**Visningsnamn:** Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper.**</span><span class="sxs-lookup"><span data-stu-id="668d0-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="668d0-166">Visningsnamnet är obligatoriskt och bör vara användarvänligt så att det är lätt att känna igen.</span><span class="sxs-lookup"><span data-stu-id="668d0-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="668d0-167">Den måste också vara unik i din domän.</span><span class="sxs-lookup"><span data-stu-id="668d0-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="668d0-168">Om du har implementerat en gruppnamnprincip måste visningsnamnet följa namnformatet som definieras av principen.</span><span class="sxs-lookup"><span data-stu-id="668d0-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="668d0-169">**Alias:** Det här är den del av e-postadressen som visas till vänster om at-symbolen (@).</span><span class="sxs-lookup"><span data-stu-id="668d0-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="668d0-170">Om du ändrar alias ändras även gruppens primära SMTP-adress och innehåller det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="668d0-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="668d0-171">Dessutom sparas e-postadressen med det tidigare aliaset som en proxyadress för gruppen.</span><span class="sxs-lookup"><span data-stu-id="668d0-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="668d0-172">**E-postadress:** E-postadressen består av alias på vänster sida av at-symbolen (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="668d0-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="668d0-173">Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="668d0-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="668d0-174">För domänvärdet klickar du på listrutan och väljer och accepterar domänen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="668d0-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="668d0-175">**Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.</span><span class="sxs-lookup"><span data-stu-id="668d0-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="668d0-176">Ägarskap</span><span class="sxs-lookup"><span data-stu-id="668d0-176">Ownership</span></span>

<span data-ttu-id="668d0-177">Använd den här fliken för att tilldela gruppägare.</span><span class="sxs-lookup"><span data-stu-id="668d0-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="668d0-178">En gruppägare kan hantera gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="668d0-178">A group owner can manage group membership.</span></span> <span data-ttu-id="668d0-179">Som standard är den person som skapar en grupp ägaren.</span><span class="sxs-lookup"><span data-stu-id="668d0-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="668d0-180">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="668d0-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="668d0-181">Om du vill lägga till ägare klickar du **på Lägg till** lägg ![ till-ikon. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="668d0-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="668d0-182">I dialogrutan som visas går du till och väljer en mottagare och klickar sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="668d0-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="668d0-183">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="668d0-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668d0-184">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="668d0-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="668d0-185">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="668d0-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="668d0-186">Medlemskap</span><span class="sxs-lookup"><span data-stu-id="668d0-186">Membership</span></span>

<span data-ttu-id="668d0-187">Använd den här fliken för att lägga till eller ta bort gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="668d0-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="668d0-188">Gruppägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="668d0-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="668d0-189">Om du vill lägga till medlemmar klickar du **på Lägg till** lägg ![ till-ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="668d0-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="668d0-190">I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="668d0-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="668d0-191">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="668d0-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668d0-192">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="668d0-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="668d0-193">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="668d0-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="668d0-194">Använda EAC för att ta bort grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="668d0-195">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="668d0-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="668d0-196">I listan över grupper markerar du distributionsgruppen som du vill ta bort och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="668d0-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="668d0-197">Använda PowerShell för att hantera grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="668d0-198">Använda fristående EOP PowerShell för att visa grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="668d0-199">Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="668d0-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="668d0-200">Om du vill returnera listan över gruppmedlemmar ersätter du den med gruppens namn, alias eller \<GroupIdentity\> e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="668d0-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="668d0-201">Detaljerad information om syntax och parametrar finns i [Get-Recipient](/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember.](/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="668d0-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="668d0-202">Använda fristående EOP PowerShell för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="668d0-203">Om du vill skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="668d0-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="668d0-204">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="668d0-204">**Notes**:</span></span>

- <span data-ttu-id="668d0-205">Parametern _Name_ är obligatorisk, har en maxlängd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="668d0-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="668d0-206">Om du inte använder _parametern DisplayName_ används värdet för _parametern Name_ för visningsnamnet.</span><span class="sxs-lookup"><span data-stu-id="668d0-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="668d0-207">Om du inte använder _parametern Alias_ används _parametern Name_ för aliasvärdet.</span><span class="sxs-lookup"><span data-stu-id="668d0-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="668d0-208">Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).</span><span class="sxs-lookup"><span data-stu-id="668d0-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="668d0-209">Om du inte använder _parametern PrimarySmtpAddress_ används aliasvärdet i _parametern PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="668d0-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="668d0-210">Om du inte använder _parametern Typ_ är standardvärdet Fördelning.</span><span class="sxs-lookup"><span data-stu-id="668d0-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="668d0-211">I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med de angivna egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="668d0-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="668d0-212">Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="668d0-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="668d0-213">Använda fristående EOP PowerShell för att ändra grupper</span><span class="sxs-lookup"><span data-stu-id="668d0-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="668d0-214">Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="668d0-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="668d0-215">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle Employees för att sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="668d0-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="668d0-216">Det här exemplet ersätter de aktuella medlemmarna i gruppen Säkerhetsgrupp med Peter Petersen och Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="668d0-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="668d0-217">I det här exemplet läggs en ny användare med namnet Tyson Fawcett till i gruppen Säkerhetsteam samtidigt som de aktuella medlemmarna i gruppen bevaras.</span><span class="sxs-lookup"><span data-stu-id="668d0-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="668d0-218">Detaljerad information om syntax och parametrar finns i [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="668d0-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="668d0-219">Ta bort en grupp med Windows PowerShell på distans</span><span class="sxs-lookup"><span data-stu-id="668d0-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="668d0-220">I det här exemplet tas distributionsgruppen IT-administratörer bort.</span><span class="sxs-lookup"><span data-stu-id="668d0-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="668d0-221">Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="668d0-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="668d0-222">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="668d0-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="668d0-223">Kontrollera att du har skapat, ändrat eller tagit bort en distributionsgrupp eller en e-postaktiverad säkerhetsgrupp genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="668d0-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="668d0-224">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="668d0-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="668d0-225">Kontrollera att gruppen visas (eller inte visas) och kontrollera **värdet för Grupptyp.**</span><span class="sxs-lookup"><span data-stu-id="668d0-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="668d0-226">Markera gruppen och visa informationen i fönstret Information, eller klicka på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="668d0-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="668d0-227">I fristående EOP PowerShell kör du följande kommando för att verifiera att gruppen visas (eller inte finns med):</span><span class="sxs-lookup"><span data-stu-id="668d0-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="668d0-228">Ersätt \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="668d0-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="668d0-229">Om du vill visa gruppens medlemmar \<GroupIdentity\> ersätter du den med gruppens namn, alias eller e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="668d0-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```