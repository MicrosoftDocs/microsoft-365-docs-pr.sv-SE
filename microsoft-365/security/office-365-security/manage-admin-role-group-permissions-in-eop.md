---
title: Hantera roll grupper i EOP
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
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan läsa mer om hur du tilldelar eller tar bort behörigheter i administrations centret för Exchange (UK) i Exchange Online Protection.
ms.openlocfilehash: fb1e0979b77c38d852f35817e01135af888eac68
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201907"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="6e975-103">Hantera rollgrupper i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="6e975-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6e975-104">I fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan du använda administrations centret för Exchange (UK) för att lägga till användare i roll grupper.</span><span class="sxs-lookup"><span data-stu-id="6e975-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="6e975-105">Om du lägger till en användare i en roll grupp får användaren behörighet att utföra särskilda administratörs uppgifter.</span><span class="sxs-lookup"><span data-stu-id="6e975-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="6e975-106">Du kan också ta bort användare från roll grupper.</span><span class="sxs-lookup"><span data-stu-id="6e975-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="6e975-107">Mer information om roller och roll grupper finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6e975-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6e975-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6e975-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6e975-109">Om du vill öppna administrations centret för Exchange (UK) läser du [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6e975-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6e975-110">Information om hur du öppnar fristående EOP PowerShell finns i [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6e975-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6e975-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="6e975-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6e975-112">Du behöver bara rollen roll hantering, som är tilldelad till rollen i (globala administratörer) som standard.</span><span class="sxs-lookup"><span data-stu-id="6e975-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="6e975-113">Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6e975-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="6e975-114">Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6e975-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6e975-115">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="6e975-115">Having problems?</span></span> <span data-ttu-id="6e975-116">Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span><span class="sxs-lookup"><span data-stu-id="6e975-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="6e975-117">Använda UK för att hantera roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="6e975-118">Använda roll grupperna UK för att Visa</span><span class="sxs-lookup"><span data-stu-id="6e975-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="6e975-119">Gå till **Permissions** \> **rollerna för administratörs**behörighet i UK.</span><span class="sxs-lookup"><span data-stu-id="6e975-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="6e975-120">Alla roll grupper i din organisation visas här.</span><span class="sxs-lookup"><span data-stu-id="6e975-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="6e975-121">Välj en roll grupp.</span><span class="sxs-lookup"><span data-stu-id="6e975-121">Select a role group.</span></span> <span data-ttu-id="6e975-122">I informations fönstret visas **namnet**, **beskrivningen**, **tilldelade roller**och **som hanteras av** roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="6e975-123">Du kan också se informationen genom att klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="6e975-124">Använda UK för att skapa roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="6e975-125">När du skapar en ny roll grupp kan du konfigurera alla inställningar själv (när du skapar gruppen eller efter).</span><span class="sxs-lookup"><span data-stu-id="6e975-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="6e975-126">Eller så kan du kopiera en befintlig roll grupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="6e975-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="6e975-127">Gå **till** \> **Administratörs roller**i UK och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="6e975-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="6e975-128">**Skapa en ny roll grupp manuellt**: Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="6e975-129">**Kopiera en befintlig roll grupp**: Välj den roll grupp som du vill kopiera och klicka sedan på **Kopiera** ![ kopierings ikon ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="6e975-130">I fönstret **ny roll grupp** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6e975-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="6e975-131">**Namn**: Ange ett unikt namn för roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="6e975-132">**Beskrivning**: Ange en valfri beskrivning för roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="6e975-133">**Roller**: Klicka på **Lägg** till ![ ikonen lägg till ](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) för att välja eller ändra de roller som är tilldelade till roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="6e975-134">**Medlemmar**: Klicka på **Lägg** till ![ ikonen lägg till ](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) om du vill ändra medlemskap i roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="6e975-135">När du är klar klickar du på **Spara** för att skapa roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="6e975-136">Använda UK för att ändra roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="6e975-137">I avsnittet UK går du till **behörigheter för behörighets** \> **Administration**, väljer den roll grupp som du vill ändra och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="6e975-138">Samma alternativ är tillgängliga när du ändrar roll grupper som när du skapar roll grupper.</span><span class="sxs-lookup"><span data-stu-id="6e975-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="6e975-139">Du kan:</span><span class="sxs-lookup"><span data-stu-id="6e975-139">You can:</span></span>

- <span data-ttu-id="6e975-140">Ändra namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="6e975-140">Change the name and description.</span></span>

- <span data-ttu-id="6e975-141">Lägga till och ta bort hanterings roller (skapa eller ta bort roll tilldelningar).</span><span class="sxs-lookup"><span data-stu-id="6e975-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="6e975-142">Lägga till och ta bort medlemmar.</span><span class="sxs-lookup"><span data-stu-id="6e975-142">Add and remove members.</span></span>

<span data-ttu-id="6e975-143">**Obs!** vissa roll grupper (till exempel organisations hantering) begränsar vilka roller du kan ta bort från gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="6e975-144">Använda UK ändra listan över medlemmar i roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="6e975-145">Gå **till** \> **Administratörs roller**i UK, Välj den roll grupp som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="6e975-146">Gör något av följande i avsnittet **medlemmar** på sidan roll grupp egenskaper som öppnas:</span><span class="sxs-lookup"><span data-stu-id="6e975-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="6e975-147">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="6e975-148">Leta reda på den användare som Wou vill lägga till på sidan som visas och klicka sedan på **Lägg till >**.</span><span class="sxs-lookup"><span data-stu-id="6e975-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="6e975-149">Välj användare och klicka på **Lägg till >** många gånger efter behov.</span><span class="sxs-lookup"><span data-stu-id="6e975-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="6e975-150">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e975-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="6e975-151">Markera de användare som du vill ta bort och klicka sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="6e975-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="6e975-152">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6e975-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6e975-153">Användarna kan behöva logga ut och logga in igen för att se ändringarna i deras administrativa rättigheter efter att du har lagt till eller tagit bort medlemmar från roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="6e975-154">Använda UK för att ta bort roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="6e975-155">Det går inte att ta bort inbyggda roll grupper, men du kan ta bort anpassade roll grupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="6e975-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="6e975-156">Gå till **Permissions** \> **rollerna för administratörs**behörighet i UK.</span><span class="sxs-lookup"><span data-stu-id="6e975-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="6e975-157">Välj den roll grupp du vill ta bort och klicka sedan på **ta bort** ![ ikon för borttagning ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6e975-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="6e975-158">Klicka på **Ja** i bekräftelse fönstret som visas.</span><span class="sxs-lookup"><span data-stu-id="6e975-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="6e975-159">Använda PowerShell för att hantera roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="6e975-160">Använd fristående EOP PowerShell för att Visa roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="6e975-161">Använd följande syntax för att visa en roll grupp:</span><span class="sxs-lookup"><span data-stu-id="6e975-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="6e975-162">I det här exemplet returneras en sammanfattnings lista över alla roll grupper.</span><span class="sxs-lookup"><span data-stu-id="6e975-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="6e975-163">Det här exemplet returnerar detaljerad information för roll gruppen som heter mottagare.</span><span class="sxs-lookup"><span data-stu-id="6e975-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="6e975-164">I det här exemplet returneras alla roll grupper där användaren Julia är medlem.</span><span class="sxs-lookup"><span data-stu-id="6e975-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="6e975-165">Du måste använda värdet för DistinguishedName (DN) för Julia, som du kan söka efter genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="6e975-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="6e975-166">Detaljerad information om syntax och parametrar finns i [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="6e975-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="6e975-167">Använda fristående EOP PowerShell för att skapa roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="6e975-168">När du skapar en ny roll grupp kan du konfigurera alla inställningar manuellt (när du skapar gruppen eller efter).</span><span class="sxs-lookup"><span data-stu-id="6e975-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="6e975-169">Eller så kan du kopiera en befintlig roll grupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="6e975-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="6e975-170">Använd följande syntax för att manuellt skapa en ny roll grupp:</span><span class="sxs-lookup"><span data-stu-id="6e975-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="6e975-171">Parametern _roles_ anger de hanterings roller som ska tilldelas roll gruppen genom att använda följande syntax `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="6e975-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="6e975-172">Du kan se tillgängliga roller med cmdleten **Get-ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="6e975-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="6e975-173">Parametern _members_ anger medlemmar i roll gruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="6e975-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="6e975-174">Du kan ange användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).</span><span class="sxs-lookup"><span data-stu-id="6e975-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="6e975-175">I det här exemplet skapas en ny roll grupp med namnet "begränsad mottagar hantering" med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6e975-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="6e975-176">Rollen e-postmottagare är tilldelad roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="6e975-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="6e975-177">Användare Kim och Martin läggs till som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="6e975-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="6e975-178">Gör så här om du vill kopiera en befintlig roll grupp:</span><span class="sxs-lookup"><span data-stu-id="6e975-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="6e975-179">Lagra den roll grupp som du vill kopiera med hjälp av följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6e975-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="6e975-180">Skapa den nya roll gruppen med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6e975-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="6e975-181">Parametern _members_ anger medlemmar i roll gruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="6e975-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="6e975-182">Du kan ange användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).</span><span class="sxs-lookup"><span data-stu-id="6e975-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="6e975-183">I det här exemplet kopieras roll gruppen organisations hantering till den nya roll gruppen "begränsad organisations hantering".</span><span class="sxs-lookup"><span data-stu-id="6e975-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="6e975-184">Medlemmar i roll gruppen är Isabelle, Cartere och Lukas.</span><span class="sxs-lookup"><span data-stu-id="6e975-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="6e975-185">Detaljerad information om syntax och parametrar finns i [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="6e975-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="6e975-186">Använda fristående EOP PowerShell ändra listan över medlemmar i roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="6e975-187">Cmdletarna **Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar ett i taget.</span><span class="sxs-lookup"><span data-stu-id="6e975-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="6e975-188">Cmdleten **Update-RoleGroupMember** kan ersätta eller ändra befintlig lista över medlemmar.</span><span class="sxs-lookup"><span data-stu-id="6e975-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="6e975-189">Medlemmar i en roll grupp kan vara användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).</span><span class="sxs-lookup"><span data-stu-id="6e975-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="6e975-190">Använd följande syntax för att ändra medlemmar i en roll grupp:</span><span class="sxs-lookup"><span data-stu-id="6e975-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="6e975-191">Använd följande syntax för att _ersätta_ den befintliga listan över medlemmar med de värden du anger: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="6e975-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="6e975-192">Om du vill _ändra_ den befintliga listan med medlemmar kan du använda följande syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="6e975-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="6e975-193">I det här exemplet ersätts alla aktuella medlemmar i roll gruppen supportavdelning med de angivna användarna.</span><span class="sxs-lookup"><span data-stu-id="6e975-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="6e975-194">I det här exemplet läggs Daigoro Akai och tas bort från listan med medlemmar i roll gruppen supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="6e975-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="6e975-195">Detaljerad information om syntax och parametrar finns i [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="6e975-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="6e975-196">Använd fristående EOP-PowerShell för att ta bort roll grupper</span><span class="sxs-lookup"><span data-stu-id="6e975-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="6e975-197">Det går inte att ta bort inbyggda roll grupper, men du kan ta bort anpassade roll grupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="6e975-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="6e975-198">Använd följande syntax för att ta bort en anpassad roll grupp:</span><span class="sxs-lookup"><span data-stu-id="6e975-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="6e975-199">I det här exemplet tas roll gruppen utbildnings administratörer bort.</span><span class="sxs-lookup"><span data-stu-id="6e975-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="6e975-200">Detaljerad information om syntax och parametrar finns i [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="6e975-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6e975-201">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="6e975-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="6e975-202">Om du vill kontrol lera att du har kopierat en roll grupp gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="6e975-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="6e975-203">Gå **till** \> **Administratörs rollerna**i UK och kontrol lera att roll gruppen är listad (eller inte listad).</span><span class="sxs-lookup"><span data-stu-id="6e975-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="6e975-204">Välj roll gruppen och kontrol lera inställningarna i informations fönstret eller klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) för att bekräfta inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6e975-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="6e975-205">I Exchange Online PowerShell ersätter du \<Role Group Name\> namnet på roll gruppen och kör följande kommando för att kontrol lera att roll gruppen finns (eller inte existerar) och verifierar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="6e975-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
