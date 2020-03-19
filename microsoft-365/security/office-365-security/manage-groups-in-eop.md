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
description: Du kan använda EOP (Exchange Online Protection) för att skapa e-postaktiverade grupper för en Exchange-organisation. Du kan också använda EOP för att definiera eller uppdatera gruppegenskaper som anger medlemskap, e-postadresser och andra aspekter av grupper.
ms.openlocfilehash: ad07066906f78703c568850afbfa5dfa8d8cc3c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806471"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="b23e8-104">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="b23e8-104">Manage groups in EOP</span></span>

 <span data-ttu-id="b23e8-105">Du kan använda EOP (Exchange Online Protection) för att skapa e-postaktiverade grupper för en Exchange-organisation.</span><span class="sxs-lookup"><span data-stu-id="b23e8-105">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="b23e8-106">Du kan också använda EOP för att definiera eller uppdatera gruppegenskaper som anger medlemskap, e-postadresser och andra aspekter av grupper.</span><span class="sxs-lookup"><span data-stu-id="b23e8-106">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="b23e8-107">Du kan skapa distributionsgrupper och säkerhetsgrupper, beroende på dina behov.</span><span class="sxs-lookup"><span data-stu-id="b23e8-107">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="b23e8-108">Dessa grupper kan skapas med hjälp av Exchange admin center (EAC) eller via fjärr-Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b23e8-108">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="b23e8-109">Typer av postaktiverade grupper</span><span class="sxs-lookup"><span data-stu-id="b23e8-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="b23e8-110">Du kan skapa två typer av grupper för exchange-organisationen:</span><span class="sxs-lookup"><span data-stu-id="b23e8-110">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="b23e8-111">Distributionsgrupper är samlingar av e-postanvändare, till exempel ett team eller annan ad hoc-grupp, som behöver ta emot eller skicka e-post angående ett gemensamt intresseområde.</span><span class="sxs-lookup"><span data-stu-id="b23e8-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="b23e8-112">Distributionsgrupper är endast för att distribuera e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b23e8-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="b23e8-113">I EOP refererar en distributionsgrupp till en postaktiverad grupp, oavsett om den har en säkerhetskontext eller inte.</span><span class="sxs-lookup"><span data-stu-id="b23e8-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="b23e8-114">Säkerhetsgrupper är samlingar av e-postanvändare som behöver åtkomstbehörigheter för administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="b23e8-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="b23e8-115">Du kanske till exempel vill ge specifika behörigheter för användares administratörsroll så att de kan konfigurera inställningar för skräppost och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="b23e8-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b23e8-116">Som standard kräver alla nya e-postaktiverade säkerhetsgrupper att alla avsändare autentiseras.</span><span class="sxs-lookup"><span data-stu-id="b23e8-116">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="b23e8-117">Detta förhindrar att externa avsändare skickar meddelanden till e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b23e8-117">This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b23e8-118">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b23e8-118">Before you begin</span></span>

- <span data-ttu-id="b23e8-119">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="b23e8-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b23e8-120">Om du vill se vilka behörigheter du behöver läser du posten "Distributionsgrupper och säkerhetsgrupper" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="b23e8-120">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="b23e8-121">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b23e8-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b23e8-122">Tänk på att när du skapar och hanterar grupper med Exchange Online Protection PowerShell cmdlets kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="b23e8-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="b23e8-123">PowerShell-procedurerna i det här avsnittet använder en batchbearbetningsmetod som resulterar i en förökningsfördröjning på några minuter innan kommandonas resultat visas.</span><span class="sxs-lookup"><span data-stu-id="b23e8-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b23e8-124">Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b23e8-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b23e8-125">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b23e8-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b23e8-126">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="b23e8-126">Having problems?</span></span> <span data-ttu-id="b23e8-127">Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="b23e8-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="b23e8-128">Skapa en grupp i EAC</span><span class="sxs-lookup"><span data-stu-id="b23e8-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="b23e8-129">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="b23e8-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b23e8-130">Klicka **New** ![på](../../media/ITPro-EAC-AddIcon.gif)Ny lägg till ikon och sedan på **Distributionsgrupp** eller **säkerhetsgrupp**, beroende på dina behov.</span><span class="sxs-lookup"><span data-stu-id="b23e8-130">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="b23e8-131">Konfigurera följande inställningar på sidan **Ny distributionsgrupp** eller **Ny säkerhetsgrupp:**</span><span class="sxs-lookup"><span data-stu-id="b23e8-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="b23e8-132">**Visningsnamn:** Skriv ett visningsnamn som är unikt för din organisation och meningsfullt för EOP-användare.</span><span class="sxs-lookup"><span data-stu-id="b23e8-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="b23e8-133">Visningsnamnet krävs.</span><span class="sxs-lookup"><span data-stu-id="b23e8-133">The display name is required.</span></span>

   - <span data-ttu-id="b23e8-134">**Alias**: Skriv ett gruppalias på upp till 64 tecken som är unikt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="b23e8-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="b23e8-135">EOP-användare skriver aliaset i raden Till: e-postmeddelanden och aliaset matchar gruppens visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="b23e8-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="b23e8-136">Om du ändrar aliasändras även den primära SMTP-adressen för gruppen och innehåller det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="b23e8-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="b23e8-137">Aliaset krävs.</span><span class="sxs-lookup"><span data-stu-id="b23e8-137">The alias is required.</span></span>

   - <span data-ttu-id="b23e8-138">**Beskrivning**: Skriv en beskrivning av gruppen så att användarna känner till syftet med gruppen.</span><span class="sxs-lookup"><span data-stu-id="b23e8-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="b23e8-139">**Ägare:** Som standard är den person som skapar gruppen ägare.</span><span class="sxs-lookup"><span data-stu-id="b23e8-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="b23e8-140">Du kan lägga till en](../../media/ITPro-EAC-AddIcon.gif)ägare genom att välja Lägg **till** ![lägg till ikon .</span><span class="sxs-lookup"><span data-stu-id="b23e8-140">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="b23e8-141">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="b23e8-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b23e8-142">Ägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="b23e8-142">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="b23e8-143">**Medlemmar**: Använd det här avsnittet för att lägga till gruppmedlemmar och ange om godkännande krävs för att personer ska kunna gå med i eller lämna gruppen.</span><span class="sxs-lookup"><span data-stu-id="b23e8-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="b23e8-144">Om du vill lägga till medlemmar](../../media/ITPro-EAC-AddIcon.gif)i gruppen klickar du på Lägg **till** ![lägg till ikon .</span><span class="sxs-lookup"><span data-stu-id="b23e8-144">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="b23e8-145">Klicka på **OK** om du vill gå tillbaka till den ursprungliga sidan.</span><span class="sxs-lookup"><span data-stu-id="b23e8-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="b23e8-146">När du är klar klickar du på **Spara** för att skapa gruppen.</span><span class="sxs-lookup"><span data-stu-id="b23e8-146">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="b23e8-147">Den nya gruppen ska visas i listan över grupper.</span><span class="sxs-lookup"><span data-stu-id="b23e8-147">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="b23e8-148">Redigera eller ta bort en grupp i EAC</span><span class="sxs-lookup"><span data-stu-id="b23e8-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="b23e8-149">Navigera till \> **mottagargrupper** **Recipients** i EAC.</span><span class="sxs-lookup"><span data-stu-id="b23e8-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="b23e8-150">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="b23e8-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="b23e8-151">Så här redigerar du en grupp: I listan med grupper klickar du på den grupp](../../media/ITPro-EAC-EditIcon.gif)som du vill visa eller ändra och klickar sedan på **Redigera** ![redigera ikon .</span><span class="sxs-lookup"><span data-stu-id="b23e8-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="b23e8-152">Du kan uppdatera allmänna inställningar, lägga till eller ta bort gruppägare och lägga till eller ta bort gruppmedlemmar efter behov.</span><span class="sxs-lookup"><span data-stu-id="b23e8-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="b23e8-153">Om du vill ta bort en grupp: Markera gruppen och klicka på **Ta bort** ![ikonen](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="b23e8-153">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b23e8-154">När du är klar med ändringarna klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b23e8-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b23e8-155">Skapa, redigera eller ta bort en grupp med fjärranslutna Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b23e8-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b23e8-156">Det här avsnittet innehåller information om hur du skapar grupper och ändrar deras egenskaper i Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b23e8-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="b23e8-157">Den visar också hur du tar bort en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="b23e8-157">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b23e8-158">Skapa en grupp med fjärranslutna Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b23e8-158">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b23e8-159">I det här exemplet används cmdleten [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) för att skapa en distributionsgrupp med ett alias för itadmin och namnet IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="b23e8-159">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="b23e8-160">Det lägger också till användare som medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="b23e8-160">It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="b23e8-161">**Om**du vill skapa en säkerhetsgrupp i stället `Security` för en distributionsgrupp använder du värdet för parametern *Typ.*</span><span class="sxs-lookup"><span data-stu-id="b23e8-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="b23e8-162">Om du vill kontrollera att du har skapat GRUPPEN IT-administratörer kör du följande kommando för att visa information om den nya gruppen:</span><span class="sxs-lookup"><span data-stu-id="b23e8-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="b23e8-163">Detaljerad syntax och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="b23e8-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="b23e8-164">Om du vill hämta en lista över medlemmar i gruppen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b23e8-164">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="b23e8-165">Detaljerad syntax- och parameterinformation finns i [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="b23e8-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="b23e8-166">Om du vill få en fullständig lista över alla dina grupper kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b23e8-166">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b23e8-167">Ändra egenskaperna för en grupp med fjärranslutna Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b23e8-167">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b23e8-168">En fördel med att använda PowerShell i stället för EAC är möjligheten att ändra egenskaper för flera grupper.</span><span class="sxs-lookup"><span data-stu-id="b23e8-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="b23e8-169">Här är några exempel på hur du använder PowerShell för Exchange Online Protection för att ändra gruppegenskaper.</span><span class="sxs-lookup"><span data-stu-id="b23e8-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="b23e8-170">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle-anställda för att sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b23e8-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="b23e8-171">Detaljerad syntax- och parameterinformation finns i [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="b23e8-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="b23e8-172">Om du vill kontrollera att du har ändrat egenskaperna för gruppen kör du följande kommando för att verifiera det nya värdet:</span><span class="sxs-lookup"><span data-stu-id="b23e8-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="b23e8-173">I det här exemplet uppdateras alla medlemmar i gruppen Seattle Anställda.</span><span class="sxs-lookup"><span data-stu-id="b23e8-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="b23e8-174">Använd ett kommatecken för att skilja alla medlemmar åt.</span><span class="sxs-lookup"><span data-stu-id="b23e8-174">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="b23e8-175">Detaljerad syntax- och parameterinformation finns i [Uppdatera-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="b23e8-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="b23e8-176">Om du vill hämta listan över alla medlemmar i gruppen Seattle-anställda kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b23e8-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="b23e8-177">Ta bort en grupp med fjärranslutna Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b23e8-177">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="b23e8-178">I det här exemplet används distributionsgruppen IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="b23e8-178">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="b23e8-179">Detaljerad syntax- och parameterinformation finns i [Ta bort-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="b23e8-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="b23e8-180">Om du vill kontrollera att gruppen har tagits bort kör du följande kommando och bekräftar att gruppen (i det här fallet "It-administratörer") har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="b23e8-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
