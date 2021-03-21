---
title: Hantera rollgrupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan lära sig att tilldela eller ta bort behörigheter i administrationscentret för Exchange (EAC) i Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926886"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="14b5a-103">Hantera rollgrupper i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="14b5a-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="14b5a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="14b5a-104">**Applies to**</span></span>
-  [<span data-ttu-id="14b5a-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="14b5a-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="14b5a-106">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda administrationscentret för Exchange (EAC) för att lägga till användare i rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="14b5a-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="14b5a-107">Om du lägger till en användare i en rollgrupp får användaren behörighet att utföra särskilda administrativa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="14b5a-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="14b5a-108">Du kan också ta bort användare från rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="14b5a-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="14b5a-109">Mer information om roller och rollgrupper finns i [Behörigheter i fristående EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="14b5a-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="14b5a-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="14b5a-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="14b5a-111">Information om hur du öppnar administrationscentret för Exchange (EAC) finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="14b5a-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="14b5a-112">Information om hur du öppnar fristående EOP PowerShell finns [i Ansluta till Exchange Online Protection PowerShell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="14b5a-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="14b5a-113">Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="14b5a-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="14b5a-114">Specifikt måste du ha **rollhanteringsrollen** som tilldelas **rollgruppen** Organisationshantering som standard.</span><span class="sxs-lookup"><span data-stu-id="14b5a-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="14b5a-115">Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="14b5a-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="14b5a-116">Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="14b5a-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="14b5a-117">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="14b5a-117">Having problems?</span></span> <span data-ttu-id="14b5a-118">Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="14b5a-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="14b5a-119">Använda EAC för att hantera rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="14b5a-120">Använda EAC för att visa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="14b5a-121">Gå till Behörighetsadministratörsroller **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="14b5a-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="14b5a-122">Här visas alla rollgrupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="14b5a-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="14b5a-123">Välj en rollgrupp.</span><span class="sxs-lookup"><span data-stu-id="14b5a-123">Select a role group.</span></span> <span data-ttu-id="14b5a-124">I fönstret Information visas **rollgruppens**  **namn,** beskrivning, tilldelade **roller** och hanterad av.</span><span class="sxs-lookup"><span data-stu-id="14b5a-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="14b5a-125">Du kan även visa den här informationen genom att klicka **på redigera** ![ redigeringsikonen ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="14b5a-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="14b5a-126">Använda EAC för att skapa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="14b5a-127">När du skapar en ny rollgrupp kan du konfigurera alla inställningar själv (när du skapar gruppen eller efter).</span><span class="sxs-lookup"><span data-stu-id="14b5a-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="14b5a-128">Du kan också kopiera en befintlig rollgrupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="14b5a-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="14b5a-129">I EAC går  du till \> **Behörighetsadministratörsroller** och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="14b5a-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="14b5a-130">**Skapa en ny rollgrupp manuellt:** Klicka på Lägg **till lägg** ![ till-ikon ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="14b5a-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="14b5a-131">**Kopiera en befintlig rollgrupp**: Välj den rollgrupp som du vill kopiera och klicka sedan på **kopiera-ikonen** ![ ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="14b5a-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="14b5a-132">I fönstret **Ny rollgrupp** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="14b5a-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="14b5a-133">**Namn**: Ange ett unikt namn för rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="14b5a-134">**Beskrivning**: Ange en valfri beskrivning av rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="14b5a-135">**Roller:** Klicka på **Lägg** till lägg till-ikon eller ta bort-ikonen för att välja eller ändra ![ de roller som är tilldelade till ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="14b5a-136">**Medlemmar:** Klicka på Ikonen **Lägg** ![ till eller ta bort ](../../media/ITPro-EAC-AddIcon.png) **ikon** för att ändra medlemskap ![ i ](../../media/ITPro-EAC-RemoveIcon.gif) rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="14b5a-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="14b5a-137">När du är klar klickar du på **Spara** för att skapa rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="14b5a-138">Använda EAC för att ändra rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="14b5a-139">I EAC går  du till \> **Behörighetsadministratörsroller**, väljer den rollgrupp du vill ändra och klickar sedan på **Redigera redigera-ikonen** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="14b5a-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="14b5a-140">Samma alternativ är tillgängliga när du ändrar rollgrupper som när du skapar rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="14b5a-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="14b5a-141">Du kan:</span><span class="sxs-lookup"><span data-stu-id="14b5a-141">You can:</span></span>

- <span data-ttu-id="14b5a-142">Ändra namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="14b5a-142">Change the name and description.</span></span>

- <span data-ttu-id="14b5a-143">Lägga till och ta bort hanteringsroller (skapa eller ta bort rolltilldelningar).</span><span class="sxs-lookup"><span data-stu-id="14b5a-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="14b5a-144">Lägga till och ta bort medlemmar.</span><span class="sxs-lookup"><span data-stu-id="14b5a-144">Add and remove members.</span></span>

<span data-ttu-id="14b5a-145">**Obs!** Vissa rollgrupper (till exempel Organisationshantering) begränsar de roller som du kan ta bort från gruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="14b5a-146">Använd EAC för att ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="14b5a-147">I EAC går du **till** \> **Behörighetsadministratörsroller**, väljer den rollgrupp som du vill ändra och klickar sedan på **Redigera redigera-ikonen.** ![ ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="14b5a-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="14b5a-148">Gör något av följande i avsnittet Medlemmar på **sidan Med** egenskaper för rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="14b5a-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="14b5a-149">Klicka på **Ikonen Lägg** till ![ lägg ](../../media/ITPro-EAC-AddIcon.png) till.</span><span class="sxs-lookup"><span data-stu-id="14b5a-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="14b5a-150">Leta rätt på den användare som du vill lägga till på sidan som visas och klicka sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="14b5a-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="14b5a-151">Välj användare och klicka **på lägg >** gånger som behövs.</span><span class="sxs-lookup"><span data-stu-id="14b5a-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="14b5a-152">När du är klar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="14b5a-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="14b5a-153">Markera de användare som du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.</span><span class="sxs-lookup"><span data-stu-id="14b5a-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="14b5a-154">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="14b5a-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="14b5a-155">Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="14b5a-156">Använda EAC för att ta bort rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="14b5a-157">Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="14b5a-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="14b5a-158">Gå till Behörighetsadministratörsroller **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="14b5a-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="14b5a-159">Markera den rollgrupp du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-DeleteIcon.png) bort.</span><span class="sxs-lookup"><span data-stu-id="14b5a-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="14b5a-160">Klicka **på** Ja i bekräftelsefönstret som visas.</span><span class="sxs-lookup"><span data-stu-id="14b5a-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="14b5a-161">Använda PowerShell för att hantera rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="14b5a-162">Använda fristående EOP PowerShell för att visa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="14b5a-163">Använd följande syntax för att visa en rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="14b5a-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="14b5a-164">Det här exemplet returnerar en sammanfattningslista över alla rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="14b5a-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="14b5a-165">I det här exemplet returneras detaljerad information om rollgruppen med namnet Mottagaradministratörer.</span><span class="sxs-lookup"><span data-stu-id="14b5a-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="14b5a-166">I det här exemplet returneras alla rollgrupper där användaren Julia är medlem.</span><span class="sxs-lookup"><span data-stu-id="14b5a-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="14b5a-167">Du måste använda värdet DistinguishedName (DN) för Julia, som du hittar genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="14b5a-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="14b5a-168">Detaljerad information om syntax och parametrar finns i [Get-RoleGroup.](/powershell/module/exchange/Get-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="14b5a-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="14b5a-169">Använda fristående EOP PowerShell för att skapa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="14b5a-170">När du skapar en ny rollgrupp kan du konfigurera alla inställningar manuellt (när gruppen skapas eller efter).</span><span class="sxs-lookup"><span data-stu-id="14b5a-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="14b5a-171">Du kan också kopiera en befintlig rollgrupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="14b5a-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="14b5a-172">Om du vill skapa en ny rollgrupp manuellt använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="14b5a-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="14b5a-173">_Parametern_ Roles anger de hanteringsroller som ska tilldelas rollgruppen med hjälp av följande `"Role1","Role1",..."RoleN"` syntax.</span><span class="sxs-lookup"><span data-stu-id="14b5a-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="14b5a-174">Du kan se tillgängliga roller med hjälp av **cmdleten Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="14b5a-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="14b5a-175">_Parametern_ Members anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="14b5a-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="14b5a-176">Du kan ange användare, e-postaktiverade säkerhetsgrupper (USG) eller andra rollgrupper (säkerhetshuvudnamn).</span><span class="sxs-lookup"><span data-stu-id="14b5a-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="14b5a-177">I det här exemplet skapas en ny rollgrupp med namnet "Hantering av begränsade mottagare" med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="14b5a-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="14b5a-178">Rollen E-postmottagare tilldelas rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="14b5a-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="14b5a-179">Användarna Kim och Martin läggs till som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="14b5a-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="14b5a-180">Så här kopierar du en befintlig rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="14b5a-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="14b5a-181">Lagra rollgruppen som du vill kopiera i en variabel med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="14b5a-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="14b5a-182">Skapa den nya rollgruppen med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="14b5a-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="14b5a-183">_Parametern_ Members anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="14b5a-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="14b5a-184">Du kan ange användare, e-postaktiverade säkerhetsgrupper (USG) eller andra rollgrupper (säkerhetshuvudnamn).</span><span class="sxs-lookup"><span data-stu-id="14b5a-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="14b5a-185">I det här exemplet kopieras rollgruppen Organisationshantering till den nya rollgruppen "Begränsad organisationshantering".</span><span class="sxs-lookup"><span data-stu-id="14b5a-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="14b5a-186">Rollgruppmedlemmarna är Isabelle, Bengt och Hansson.</span><span class="sxs-lookup"><span data-stu-id="14b5a-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="14b5a-187">Detaljerad information om syntax och parametrar finns [i New-RoleGroup.](/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="14b5a-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="14b5a-188">Använd fristående EOP PowerShell för att ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="14b5a-189">Cmdletarna **Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar en i taget.</span><span class="sxs-lookup"><span data-stu-id="14b5a-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="14b5a-190">**Cmdlet:en Update-RoleGroupMember** kan ersätta eller ändra den befintliga listan över medlemmar.</span><span class="sxs-lookup"><span data-stu-id="14b5a-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="14b5a-191">Medlemmar i en rollgrupp kan vara användare, e-postaktiverade säkerhetsgrupper (USG) eller andra rollgrupper (säkerhetsobjekt).</span><span class="sxs-lookup"><span data-stu-id="14b5a-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="14b5a-192">Använd följande syntax för att ändra medlemmarna i en rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="14b5a-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="14b5a-193">Använd _följande_ syntax för att ersätta den befintliga listan med medlemmar med de värden du anger: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="14b5a-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="14b5a-194">Använd följande syntax _för_ att selektivt ändra den befintliga listan med medlemmar: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="14b5a-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="14b5a-195">Det här exemplet ersätter alla aktuella medlemmar i rollgruppen för supportavdelningen med angivna användare.</span><span class="sxs-lookup"><span data-stu-id="14b5a-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="14b5a-196">I det här exemplet läggs Daigoro Ack till och Valerie Barrio tas bort från listan över medlemmar i rollgruppen Supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="14b5a-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="14b5a-197">Detaljerad information om syntax och parametrar finns i [Update-RoleGroupMember.](/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="14b5a-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="14b5a-198">Använda fristående EOP PowerShell för att ta bort rollgrupper</span><span class="sxs-lookup"><span data-stu-id="14b5a-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="14b5a-199">Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="14b5a-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="14b5a-200">Använd följande syntax för att ta bort en anpassad rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="14b5a-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="14b5a-201">I det här exemplet tas rollgruppen Utbildningsadministratörer bort.</span><span class="sxs-lookup"><span data-stu-id="14b5a-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="14b5a-202">Detaljerad information om syntax och parametrar finns i [Remove-RoleGroup.](/powershell/module/exchange/Remove-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="14b5a-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="14b5a-203">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="14b5a-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="14b5a-204">Kontrollera att du har kopierat en rollgrupp genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="14b5a-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="14b5a-205">I EAC går  du till \> **Behörighetsadministratörsroller** och kontrollerar att rollgruppen visas (eller inte visas).</span><span class="sxs-lookup"><span data-stu-id="14b5a-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="14b5a-206">Markera rollgruppen och kontrollera inställningarna i fönstret Information eller klicka på Redigera **redigeringsikon** ![ för att kontrollera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="14b5a-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="14b5a-207">Ersätt med namnet på rollgruppen i Exchange Online PowerShell och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och \<Role Group Name\> verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="14b5a-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```