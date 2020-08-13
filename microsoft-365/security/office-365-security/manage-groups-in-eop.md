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
description: Administratörer i fristående Exchange Online Protection (EOP)-organisationer kan lära sig hur du skapar, ändrar och tar bort distributions grupper och e-postaktiverade säkerhets grupper i administrations centret för Exchange (UK) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: 813735d4024c3b8424a6bbac51ebef7b4c53e590
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653659"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="592a8-103">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="592a8-103">Manage groups in EOP</span></span>

<span data-ttu-id="592a8-104">I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:</span><span class="sxs-lookup"><span data-stu-id="592a8-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="592a8-105">**Distributions grupper**: en samling e-postanvändare eller andra distributions grupper.</span><span class="sxs-lookup"><span data-stu-id="592a8-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="592a8-106">Teams eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse område.</span><span class="sxs-lookup"><span data-stu-id="592a8-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="592a8-107">Distributions grupper är exklusivt för att distribuera e-postmeddelanden och är inte säkerhets objekt (de kan inte ha tilldelade behörigheter).</span><span class="sxs-lookup"><span data-stu-id="592a8-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="592a8-108">**E-postaktiverade säkerhets grupper**: en samling e-postanvändare och andra säkerhets grupper som behöver åtkomst behörigheter för administratörs roller.</span><span class="sxs-lookup"><span data-stu-id="592a8-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="592a8-109">Du kanske till exempel vill ge specifika användar administratörs behörigheter så att de kan konfigurera skydd mot skräp post och inställningar mot skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="592a8-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="592a8-110">Som standard nekar nya e-postaktiverade säkerhets grupper meddelanden från externa (overifierade) avsändare.</span><span class="sxs-lookup"><span data-stu-id="592a8-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="592a8-111">Lägg inte till distributions grupper i e-postaktiverade säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="592a8-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="592a8-112">Du kan hantera grupper i administrations centret för Exchange (UK) och i fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="592a8-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="592a8-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="592a8-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="592a8-114">Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="592a8-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="592a8-115">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="592a8-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="592a8-116">När du hanterar grupper i fristående EOP PowerShell kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="592a8-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="592a8-117">PowerShell-förfarandena i det här avsnittet använder en grupp bearbetnings metod som resulterar i en spridnings fördröjning på några minuter innan resultatet av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="592a8-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="592a8-118">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="592a8-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="592a8-119">Specifikt behöver du rollen distributions grupper, som är tilldelad till roll grupperna i (global admins) och RecipientManagement som standard.</span><span class="sxs-lookup"><span data-stu-id="592a8-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="592a8-120">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="592a8-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="592a8-121">Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="592a8-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="592a8-122">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="592a8-122">Having problems?</span></span> <span data-ttu-id="592a8-123">Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="592a8-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="592a8-124">Använda administrations centret för Exchange för att hantera distributions grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="592a8-125">Använda UK för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="592a8-126">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="592a8-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="592a8-127">Klicka på **ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) och välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="592a8-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="592a8-128">**Distributions grupp**</span><span class="sxs-lookup"><span data-stu-id="592a8-128">**Distribution group**</span></span>

   - <span data-ttu-id="592a8-129">**E-postaktiverad säkerhetsgrupp**</span><span class="sxs-lookup"><span data-stu-id="592a8-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="592a8-130">Konfigurera följande inställningar på sidan ny grupp som öppnas.</span><span class="sxs-lookup"><span data-stu-id="592a8-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="592a8-131">Inställningar som är markerade med <sup>\*</sup> är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="592a8-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="592a8-132"><sup>\*</sup>**Visnings namn**: det här namnet visas i organisationens adress bok, på raden till: när e-post skickas till den här gruppen och i listan **grupper** i UK.</span><span class="sxs-lookup"><span data-stu-id="592a8-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="592a8-133">Visnings namnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att folk förstår vad det är.</span><span class="sxs-lookup"><span data-stu-id="592a8-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="592a8-134"><sup>\*</sup>**Alias**: Använd den här rutan för att ange namnet på aliaset för gruppen.</span><span class="sxs-lookup"><span data-stu-id="592a8-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="592a8-135">Aliaset får inte överstiga 64 tecken och måste vara unikt.</span><span class="sxs-lookup"><span data-stu-id="592a8-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="592a8-136">När en användare skriver alias på raden till i ett e-postmeddelande matchas gruppens visnings namn.</span><span class="sxs-lookup"><span data-stu-id="592a8-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="592a8-137"><sup>\*</sup>**E-postadress**: e-postadressen består av aliaset på vänster sida av snabel-a (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="592a8-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="592a8-138">Som standard används värdet för **alias** för Ali Aset, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="592a8-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="592a8-139">För domän värde klickar du på den nedrullningsbara List rutan och väljer och godkänner domänen i organisationen.</span><span class="sxs-lookup"><span data-stu-id="592a8-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="592a8-140">**Beskrivning**: beskrivningen visas i adress boken och i informations fönstret i UK.</span><span class="sxs-lookup"><span data-stu-id="592a8-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="592a8-141"><sup>\*</sup>**Ägare**: en grupp ägare kan hantera grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="592a8-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="592a8-142">Den person som skapar en grupp är som standard ägaren.</span><span class="sxs-lookup"><span data-stu-id="592a8-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="592a8-143">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="592a8-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="592a8-144">Om du vill lägga till ägare klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="592a8-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="592a8-145">I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="592a8-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="592a8-146">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="592a8-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="592a8-147">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="592a8-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="592a8-148">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="592a8-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="592a8-149">**Medlemmar**: lägga till och ta bort grupp medlemmar.</span><span class="sxs-lookup"><span data-stu-id="592a8-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="592a8-150">Om du vill lägga till medlemmar klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="592a8-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="592a8-151">I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="592a8-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="592a8-152">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="592a8-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="592a8-153">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="592a8-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="592a8-154">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="592a8-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="592a8-155">När du är klar klickar du på **Spara** för att skapa distributions gruppen.</span><span class="sxs-lookup"><span data-stu-id="592a8-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="592a8-156">Använda UK för att ändra distributions grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="592a8-157">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="592a8-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="592a8-158">I listan med grupper väljer du den distributions grupp eller e-postaktiverade säkerhets grupp som du vill ändra och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="592a8-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="592a8-159">På sidan Egenskaper för distributions grupp som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="592a8-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="592a8-160">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="592a8-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="592a8-161">Allmänt</span><span class="sxs-lookup"><span data-stu-id="592a8-161">General</span></span>

<span data-ttu-id="592a8-162">Använd den här fliken för att visa eller ändra grundläggande information om gruppen.</span><span class="sxs-lookup"><span data-stu-id="592a8-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="592a8-163">**Visnings namn**: det här namnet visas i adress boken, på raden till när e-post skickas till den här gruppen och i **listan grupper**.</span><span class="sxs-lookup"><span data-stu-id="592a8-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="592a8-164">Visnings namnet är obligatoriskt och bör vara användarvänligt så att folk förstår vad det är.</span><span class="sxs-lookup"><span data-stu-id="592a8-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="592a8-165">Det måste också vara unikt i din domän.</span><span class="sxs-lookup"><span data-stu-id="592a8-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="592a8-166">Om du har implementerat en grupp namns princip måste visnings namnet följa det namngivnings format som definieras av principen.</span><span class="sxs-lookup"><span data-stu-id="592a8-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="592a8-167">**Alias**: det här är den del av e-postadressen som visas till vänster om @-symbolen.</span><span class="sxs-lookup"><span data-stu-id="592a8-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="592a8-168">Om du ändrar aliaset ändras även den primära SMTP-adressen för gruppen och innehåller det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="592a8-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="592a8-169">Dessutom sparas e-postadressen med föregående alias som en proxyadress för gruppen.</span><span class="sxs-lookup"><span data-stu-id="592a8-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="592a8-170">**E-postadress**: e-postadressen består av aliaset på vänster sida av snabel-a (@) och en domän på höger sida.</span><span class="sxs-lookup"><span data-stu-id="592a8-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="592a8-171">Som standard används värdet för **alias** för Ali Aset, men du kan ändra det.</span><span class="sxs-lookup"><span data-stu-id="592a8-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="592a8-172">För domän värde klickar du på den nedrullningsbara List rutan och väljer och godkänner domänen i organisationen.</span><span class="sxs-lookup"><span data-stu-id="592a8-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="592a8-173">**Beskrivning**: beskrivningen visas i adress boken och i informations fönstret i UK.</span><span class="sxs-lookup"><span data-stu-id="592a8-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="592a8-174">Egendom</span><span class="sxs-lookup"><span data-stu-id="592a8-174">Ownership</span></span>

<span data-ttu-id="592a8-175">Använd den här fliken för att tilldela grupp ägare.</span><span class="sxs-lookup"><span data-stu-id="592a8-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="592a8-176">En grupp ägare kan hantera grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="592a8-176">A group owner can manage group membership.</span></span> <span data-ttu-id="592a8-177">Den person som skapar en grupp är som standard ägaren.</span><span class="sxs-lookup"><span data-stu-id="592a8-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="592a8-178">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="592a8-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="592a8-179">Om du vill lägga till ägare klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="592a8-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="592a8-180">Leta upp och välj en mottagare i dialog rutan som visas och klicka sedan på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="592a8-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="592a8-181">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="592a8-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="592a8-182">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="592a8-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="592a8-183">Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="592a8-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="592a8-184">Ingå</span><span class="sxs-lookup"><span data-stu-id="592a8-184">Membership</span></span>

<span data-ttu-id="592a8-185">Använd den här fliken för att lägga till eller ta bort grupp medlemmar.</span><span class="sxs-lookup"><span data-stu-id="592a8-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="592a8-186">Grupp ägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="592a8-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="592a8-187">Om du vill lägga till medlemmar klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="592a8-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="592a8-188">I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="592a8-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="592a8-189">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="592a8-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="592a8-190">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="592a8-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="592a8-191">Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="592a8-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="592a8-192">Använda UK för att ta bort grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="592a8-193">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="592a8-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="592a8-194">I listan med grupper väljer du den distributions grupp som du vill ta bort och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="592a8-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="592a8-195">Använda PowerShell för att hantera grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="592a8-196">Använd fristående EOP PowerShell för att Visa grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="592a8-197">Kör följande kommando om du vill returnera en sammanfattnings lista över alla distributions grupper och e-postaktiverade säkerhets grupper i fristående EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="592a8-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="592a8-198">Om du vill returnera listan över grupp medlemmar ersätter du \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="592a8-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="592a8-199">Detaljerad information om syntax och parametrar finns i [Get-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="592a8-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="592a8-200">Använda fristående EOP PowerShell för att skapa grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="592a8-201">Använd följande syntax för att skapa distributions grupper eller e-postaktiverade säkerhets grupper i fristående EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="592a8-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="592a8-202">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="592a8-202">**Notes**:</span></span>

- <span data-ttu-id="592a8-203">Parametern _namn_ är obligatorisk, har en maximal längd på 64 tecken och måste vara unik.</span><span class="sxs-lookup"><span data-stu-id="592a8-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="592a8-204">Om du inte använder parametern _DisplayName_ används värdet för _namn_ parametern som visnings namn.</span><span class="sxs-lookup"><span data-stu-id="592a8-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="592a8-205">Om du inte använder _Ali Aset_ används parametern _Name_ för värdet alias.</span><span class="sxs-lookup"><span data-stu-id="592a8-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="592a8-206">Blank steg tas bort och tecken som inte stöds konverteras till frågetecken (?).</span><span class="sxs-lookup"><span data-stu-id="592a8-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="592a8-207">Om du inte använder parametern _PrimarySMTPAddress_ används värdet alias i parametern _PrimarySMTPAddress_ .</span><span class="sxs-lookup"><span data-stu-id="592a8-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="592a8-208">Om du inte använder parametern _Type_ är standardvärdet distribution.</span><span class="sxs-lookup"><span data-stu-id="592a8-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="592a8-209">I det här exemplet skapas en distributions grupp som heter IT-administratörer med angivna egenskaper.</span><span class="sxs-lookup"><span data-stu-id="592a8-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="592a8-210">Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="592a8-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="592a8-211">Använda fristående EOP PowerShell för att ändra grupper</span><span class="sxs-lookup"><span data-stu-id="592a8-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="592a8-212">Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="592a8-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="592a8-213">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även för svars adress) för anställda i Stockholm till sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="592a8-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="592a8-214">Det här exemplet ersätter de aktuella medlemmarna i gruppen säkerhets team med söta Petersen och Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="592a8-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="592a8-215">I det här exemplet läggs en ny användare till som heter Tyson Fawcett till i gruppen säkerhets team samtidigt som de nuvarande medlemmarna i gruppen bevaras.</span><span class="sxs-lookup"><span data-stu-id="592a8-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="592a8-216">Detaljerad information om syntax och parametrar finns i [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="592a8-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="592a8-217">Ta bort en grupp med Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="592a8-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="592a8-218">I det här exemplet används borttagning av distributions gruppen IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="592a8-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="592a8-219">Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="592a8-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="592a8-220">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="592a8-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="592a8-221">Gör något av följande om du vill kontrol lera att du har skapat, ändrat eller tagit bort en distributions grupp eller en e-postaktive rad säkerhets grupp:</span><span class="sxs-lookup"><span data-stu-id="592a8-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="592a8-222">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="592a8-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="592a8-223">Kontrol lera att gruppen är listad (eller inte listad) och kontrol lera värdet för **grupp typ** .</span><span class="sxs-lookup"><span data-stu-id="592a8-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="592a8-224">Markera gruppen och Visa informationen i informations fönstret, eller klicka på **Redigera** ![ redigerings ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="592a8-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="592a8-225">I fristående EOP PowerShell kör du följande kommando för att kontrol lera att gruppen är listad (eller inte listad):</span><span class="sxs-lookup"><span data-stu-id="592a8-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="592a8-226">Ersätt \<GroupIdentity\> med namn, alias eller e-postadress för gruppen och kör följande kommando för att kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="592a8-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="592a8-227">Om du vill visa grupp medlemmarna ersätter du \<GroupIdentity\> gruppen med namn, alias eller e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="592a8-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
