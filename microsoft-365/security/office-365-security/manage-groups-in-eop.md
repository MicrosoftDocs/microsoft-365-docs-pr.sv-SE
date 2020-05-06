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
description: I den här artikeln får du lära dig hur du skapar och hanterar e-postaktiverade grupper för en Exchange-organisation i Exchange Online Protection (EOP).
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034408"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="70482-103">Hantera grupper i EOP</span><span class="sxs-lookup"><span data-stu-id="70482-103">Manage groups in EOP</span></span>

 <span data-ttu-id="70482-104">Du kan använda Exchange Online Protection (EOP) för att skapa e-postaktiverade grupper för en Exchange-organisation.</span><span class="sxs-lookup"><span data-stu-id="70482-104">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization.</span></span> <span data-ttu-id="70482-105">Du kan också använda EOP för att definiera eller uppdatera gruppegenskaper som anger medlemskap, e-postadresser och andra aspekter av grupper.</span><span class="sxs-lookup"><span data-stu-id="70482-105">You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups.</span></span> <span data-ttu-id="70482-106">Du kan skapa distributionsgrupper och säkerhetsgrupper, beroende på dina behov.</span><span class="sxs-lookup"><span data-stu-id="70482-106">You can create distribution groups and security groups, depending on your needs.</span></span> <span data-ttu-id="70482-107">Dessa grupper kan skapas med hjälp av Administrationscenter för Exchange (EAC) eller via fjärr-Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70482-107">These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="70482-108">Typer av e-postaktiverade grupper</span><span class="sxs-lookup"><span data-stu-id="70482-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="70482-109">Du kan skapa två typer av grupper för Exchange-organisationen:</span><span class="sxs-lookup"><span data-stu-id="70482-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="70482-110">Distributionsgrupper är samlingar av e-postanvändare, till exempel ett team eller en annan ad hoc-grupp, som behöver ta emot eller skicka e-post angående ett gemensamt intresseområde.</span><span class="sxs-lookup"><span data-stu-id="70482-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="70482-111">Distributionsgrupper är uteslutande avsedda för distribution av e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="70482-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="70482-112">I EOP refererar en distributionsgrupp till alla e-postaktiverade grupper, oavsett om den har en säkerhetskontext eller inte.</span><span class="sxs-lookup"><span data-stu-id="70482-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="70482-113">Säkerhetsgrupper är samlingar av e-postanvändare som behöver åtkomstbehörigheter för administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="70482-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="70482-114">Du kanske till exempel vill ge specifika användaradministratörsrollbehörigheter så att de kan konfigurera inställningar för skräppost och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="70482-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70482-115">Som standard kräver alla nya e-postaktiverade säkerhetsgrupper att alla avsändare autentiseras.</span><span class="sxs-lookup"><span data-stu-id="70482-115">By default, all new mail-enabled security groups require that all senders be authenticated.</span></span> <span data-ttu-id="70482-116">Detta förhindrar att externa avsändare skickar meddelanden till e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="70482-116">This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="70482-117">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="70482-117">Before you begin</span></span>

- <span data-ttu-id="70482-118">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="70482-118">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="70482-119">Information om vilka behörigheter du behöver finns i posten "Distributionsgrupper och säkerhetsgrupper" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="70482-119">To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="70482-120">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="70482-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="70482-121">Tänk på att när du skapar och hanterar grupper med hjälp av Exchange Online Protection PowerShell-cmdletar kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="70482-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="70482-122">PowerShell-procedurerna i det här avsnittet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="70482-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="70482-123">Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="70482-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="70482-124">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="70482-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="70482-125">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="70482-125">Having problems?</span></span> <span data-ttu-id="70482-126">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="70482-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="70482-127">Skapa en grupp i EAC</span><span class="sxs-lookup"><span data-stu-id="70482-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="70482-128">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="70482-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="70482-129">Klicka **New** ![på](../../media/ITPro-EAC-AddIcon.gif)Ny lägg till ikon och sedan på **Distributionsgrupp** eller **Säkerhetsgrupp**, beroende på dina behov.</span><span class="sxs-lookup"><span data-stu-id="70482-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="70482-130">Konfigurera följande inställningar på sidan **Ny distributionsgrupp** eller **Ny säkerhetsgrupp:**</span><span class="sxs-lookup"><span data-stu-id="70482-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="70482-131">**Visningsnamn**: Skriv ett visningsnamn som är unikt för din organisation och som är meningsfullt för EOP-användare.</span><span class="sxs-lookup"><span data-stu-id="70482-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="70482-132">Visningsnamnet krävs.</span><span class="sxs-lookup"><span data-stu-id="70482-132">The display name is required.</span></span>

   - <span data-ttu-id="70482-133">**Alias**: Skriv ett gruppalias med upp till 64 tecken som är unika för din organisation.</span><span class="sxs-lookup"><span data-stu-id="70482-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="70482-134">EOP-användare skriver aliaset i raden Till: och aliaset matchas till gruppens visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="70482-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="70482-135">Om du ändrar aliaset ändras även den primära SMTP-adressen för gruppen och det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="70482-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="70482-136">Alias krävs.</span><span class="sxs-lookup"><span data-stu-id="70482-136">The alias is required.</span></span>

   - <span data-ttu-id="70482-137">**Beskrivning**: Skriv en beskrivning av gruppen så att användarna vet syftet med gruppen.</span><span class="sxs-lookup"><span data-stu-id="70482-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="70482-138">**Ägare**: Som standard är den person som skapar gruppen ägaren.</span><span class="sxs-lookup"><span data-stu-id="70482-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="70482-139">Du kan lägga till en](../../media/ITPro-EAC-AddIcon.gif)ägare genom att välja Lägg **till** ![ikonen .</span><span class="sxs-lookup"><span data-stu-id="70482-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="70482-140">Alla grupper måste ha minst en ägare.</span><span class="sxs-lookup"><span data-stu-id="70482-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="70482-141">Ägare behöver inte vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="70482-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="70482-142">**Medlemmar**: Använd det här avsnittet om du vill lägga till gruppmedlemmar och ange om godkännande krävs för att personer ska kunna gå med i eller lämna gruppen.</span><span class="sxs-lookup"><span data-stu-id="70482-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="70482-143">Om du vill lägga till medlemmar](../../media/ITPro-EAC-AddIcon.gif)i gruppen klickar du på Lägg **till** ![ikonen .</span><span class="sxs-lookup"><span data-stu-id="70482-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="70482-144">Klicka på **OK** för att återgå till den ursprungliga sidan.</span><span class="sxs-lookup"><span data-stu-id="70482-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="70482-145">När du är klar klickar du på **Spara** för att skapa gruppen.</span><span class="sxs-lookup"><span data-stu-id="70482-145">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="70482-146">Den nya gruppen ska visas i listan över grupper.</span><span class="sxs-lookup"><span data-stu-id="70482-146">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="70482-147">Redigera eller ta bort en grupp i EAC</span><span class="sxs-lookup"><span data-stu-id="70482-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="70482-148">I EAC navigerar du till **mottagargrupper** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="70482-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="70482-149">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="70482-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="70482-150">Så här redigerar du en grupp: Klicka på den grupp som du vill](../../media/ITPro-EAC-EditIcon.gif)visa eller ändra i listan med grupper och klicka sedan på **Ikonen Redigera** ![redigera .</span><span class="sxs-lookup"><span data-stu-id="70482-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="70482-151">Du kan uppdatera allmänna inställningar, lägga till eller ta bort gruppägare och lägga till eller ta bort gruppmedlemmar efter behov.</span><span class="sxs-lookup"><span data-stu-id="70482-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="70482-152">Så här tar du bort en grupp: Markera gruppen och klicka på **Ta bort** ![ta bort ikon](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="70482-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="70482-153">När du är klar med ändringarna klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="70482-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="70482-154">Skapa, redigera eller ta bort en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70482-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="70482-155">Det här avsnittet innehåller information om hur du skapar grupper och ändrar deras egenskaper i Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70482-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="70482-156">Den visar också hur du tar bort en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="70482-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="70482-157">Skapa en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70482-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="70482-158">I det här exemplet används cmdleten [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) för att skapa en distributionsgrupp med ett alias itadmin och namnet IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="70482-158">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators.</span></span> <span data-ttu-id="70482-159">Det lägger också till användare som medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="70482-159">It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="70482-160">**Om**du vill skapa en säkerhetsgrupp i stället `Security` för en distributionsgrupp använder du värdet för parametern *Type.*</span><span class="sxs-lookup"><span data-stu-id="70482-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="70482-161">Om du vill kontrollera att du har skapat gruppen IT-administratörer kör du följande kommando för att visa information om den nya gruppen:</span><span class="sxs-lookup"><span data-stu-id="70482-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="70482-162">Detaljerad syntax- och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="70482-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="70482-163">Om du vill hämta en lista över medlemmar i gruppen kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="70482-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="70482-164">Detaljerad syntax- och parameterinformation finns i [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="70482-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="70482-165">Om du vill få en fullständig lista över alla dina grupper kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="70482-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="70482-166">Ändra egenskaperna för en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70482-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="70482-167">En fördel med att använda PowerShell i stället för EAC är möjligheten att ändra egenskaper för flera grupper.</span><span class="sxs-lookup"><span data-stu-id="70482-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="70482-168">Här är några exempel på hur du använder Exchange Online Protection PowerShell för att ändra gruppegenskaper.</span><span class="sxs-lookup"><span data-stu-id="70482-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="70482-169">I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle-anställda för att sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="70482-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="70482-170">Detaljerad syntax- och parameterinformation finns i [Ange-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="70482-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="70482-171">Om du vill kontrollera att du har ändrat egenskaperna för gruppen kör du följande kommando för att verifiera det nya värdet:</span><span class="sxs-lookup"><span data-stu-id="70482-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="70482-172">I det här exemplet uppdateras alla medlemmar i gruppen Seattle-anställda.</span><span class="sxs-lookup"><span data-stu-id="70482-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="70482-173">Använd ett kommatecken för att avgränsa alla medlemmar.</span><span class="sxs-lookup"><span data-stu-id="70482-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="70482-174">Detaljerad syntax- och parameterinformation finns i [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="70482-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="70482-175">Om du vill hämta listan över alla medlemmar i gruppen Seattle Employees kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="70482-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="70482-176">Ta bort en grupp med fjärr-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70482-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="70482-177">I det här exemplet tas distributionsgruppen IT-administratörer bort.</span><span class="sxs-lookup"><span data-stu-id="70482-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="70482-178">Detaljerad syntax- och parameterinformation finns i [Ta bort EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="70482-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="70482-179">Om du vill kontrollera att gruppen har tagits bort kör du följande kommando och bekräftar att gruppen (i det här fallet "It Administrators") har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="70482-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
