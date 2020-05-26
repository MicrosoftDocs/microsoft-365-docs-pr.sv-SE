---
title: Hantera rollgrupper i EOP
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
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan lära sig att tilldela eller ta bort behörigheter i Administrationscenter för Exchange (EAC) i Exchange Online Protection.
ms.openlocfilehash: ba2d053e1e75bd8867ebb9eb7f426cde92abd3e8
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352341"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="ab734-103">Hantera rollgrupper i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="ab734-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="ab734-104">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) för att lägga till användare i rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ab734-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="ab734-105">Genom att lägga till en användare i en rollgrupp får användaren behörighet att utföra specifika administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ab734-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="ab734-106">Du kan också ta bort användare från rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ab734-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="ab734-107">Mer information om roller och rollgrupper finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ab734-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ab734-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ab734-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ab734-109">Om du vill öppna Administrationscenter för Exchange (EAC) finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ab734-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ab734-110">Information om hur du öppnar fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab734-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ab734-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="ab734-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ab734-112">Du behöver rollrollen Rollhantering, som som tilldelas rollgruppen OrganizationManagement (global admins) som standard.</span><span class="sxs-lookup"><span data-stu-id="ab734-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="ab734-113">Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="ab734-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="ab734-114">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ab734-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="ab734-115">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="ab734-115">Having problems?</span></span> <span data-ttu-id="ab734-116">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="ab734-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="ab734-117">Använd EAC för att hantera rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="ab734-118">Använda EAC för att visa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="ab734-119">Gå till **Behörighetsadministratörsroller** \> **Admin roles**i EAC.</span><span class="sxs-lookup"><span data-stu-id="ab734-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="ab734-120">Alla rollgrupper i organisationen visas här.</span><span class="sxs-lookup"><span data-stu-id="ab734-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="ab734-121">Välj en rollgrupp.</span><span class="sxs-lookup"><span data-stu-id="ab734-121">Select a role group.</span></span> <span data-ttu-id="ab734-122">I fönstret Information visas **rollgruppens namn,** **beskrivning,** **tilldelade roller**och **Hanterad** av.</span><span class="sxs-lookup"><span data-stu-id="ab734-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="ab734-123">Du kan också se den **Edit** här informationen genom att klicka på ![ Ikonen Redigera redigera ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ab734-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="ab734-124">Använd EAC för att skapa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="ab734-125">När du skapar en ny rollgrupp kan du konfigurera alla inställningar själv (under skapandet av gruppen eller efter).</span><span class="sxs-lookup"><span data-stu-id="ab734-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="ab734-126">Du kan också kopiera en befintlig rollgrupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="ab734-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="ab734-127">Gå till **Behörighetsadministratörsroller** i EAC \> **Admin roles**och gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="ab734-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="ab734-128">**Skapa en ny rollgrupp manuellt:** Klicka på **Ikonen Lägg till** lägg till ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ab734-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="ab734-129">**Kopiera en befintlig rollgrupp**: Markera den rollgrupp som du vill kopiera och klicka sedan på **Ikonen Kopiera** ![ kopia ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ab734-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="ab734-130">Konfigurera följande inställningar i fönstret **Ny rollgrupp** som visas:</span><span class="sxs-lookup"><span data-stu-id="ab734-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="ab734-131">**Namn**: Ange ett unikt namn för rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="ab734-132">**Beskrivning**: Ange en valfri beskrivning för rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="ab734-133">**Roller**: Klicka på **Ikonen Lägg** till eller ![ Ta ](../../media/ITPro-EAC-AddIcon.png) **bort** ![ ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) för att markera eller ändra de roller som har tilldelats rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="ab734-134">**Medlemmar**: Klicka på **Lägg till** ikonen Lägg till eller ![ Ta ](../../media/ITPro-EAC-AddIcon.png) **bort** ![ ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) om du vill ändra rollgruppens medlemskap.</span><span class="sxs-lookup"><span data-stu-id="ab734-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="ab734-135">När du är klar klickar du på **Spara** för att skapa rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="ab734-136">Använda EAC för att ändra rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="ab734-137">Gå till **Behörighetsadministratörsroller** i EAC, \> **Admin roles**välj den rollgrupp som du vill ändra och klicka sedan på Ikonen **Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="ab734-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="ab734-138">Samma alternativ är tillgängliga när du ändrar rollgrupper som när du skapar rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ab734-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="ab734-139">Du kan:</span><span class="sxs-lookup"><span data-stu-id="ab734-139">You can:</span></span>

- <span data-ttu-id="ab734-140">Ändra namn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ab734-140">Change the name and description.</span></span>

- <span data-ttu-id="ab734-141">Lägga till och ta bort hanteringsroller (skapa eller ta bort rolltilldelningar).</span><span class="sxs-lookup"><span data-stu-id="ab734-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="ab734-142">Lägg till och ta bort medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ab734-142">Add and remove members.</span></span>

<span data-ttu-id="ab734-143">**Vissa**rollgrupper (till exempel Organisationshantering) begränsar de roller som du kan ta bort från gruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="ab734-144">Använda EAC ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="ab734-145">Gå till **Behörighetsadministratörsroller** i \> **Admin roles**EAC, välj den rollgrupp som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="ab734-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="ab734-146">Gör något av följande i avsnittet **Memebers** i egenskapssidan för rollgrupp som öppnas:</span><span class="sxs-lookup"><span data-stu-id="ab734-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="ab734-147">Klicka på **Lägg till** ikonen För lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ab734-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="ab734-148">På sidan som visas hittar du den användare som wou vill lägga till och klickar sedan på **lägg till ->**.</span><span class="sxs-lookup"><span data-stu-id="ab734-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="ab734-149">Markera användare och klicka på **Lägg till ->** många gånger om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ab734-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="ab734-150">När du är klar klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab734-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ab734-151">Markera de användare som du vill ta bort och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="ab734-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="ab734-152">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ab734-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab734-153">Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="ab734-154">Använd EAC för att ta bort rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="ab734-155">Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="ab734-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="ab734-156">Gå till **Behörighetsadministratörsroller** \> **Admin roles**i EAC.</span><span class="sxs-lookup"><span data-stu-id="ab734-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="ab734-157">Markera den rollgrupp som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ab734-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="ab734-158">Klicka på **Ja** i bekräftelsefönstret som visas.</span><span class="sxs-lookup"><span data-stu-id="ab734-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="ab734-159">Använda PowerShell för att hantera rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="ab734-160">Använda fristående EOP PowerShell för att visa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="ab734-161">Om du vill visa en rollgrupp använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="ab734-162">I det här exemplet returneras en sammanfattningslista över alla rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="ab734-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="ab734-163">I det här exemplet returneras detaljerad information för rollgruppen Med namnet Mottagaradministratörer.</span><span class="sxs-lookup"><span data-stu-id="ab734-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="ab734-164">I det här exemplet returneras alla rollgrupper där användaren Julia är medlem.</span><span class="sxs-lookup"><span data-stu-id="ab734-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="ab734-165">Du måste använda värdet DistinguishedName (DN) för Julia, som du kan hitta genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="ab734-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="ab734-166">Detaljerad syntax- och parameterinformation finns i [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="ab734-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="ab734-167">Använda fristående EOP PowerShell för att skapa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="ab734-168">När du skapar en ny rollgrupp kan du konfigurera alla inställningar manuellt (under skapandet av gruppen eller efter).</span><span class="sxs-lookup"><span data-stu-id="ab734-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="ab734-169">Du kan också kopiera en befintlig rollgrupp och ändra den.</span><span class="sxs-lookup"><span data-stu-id="ab734-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="ab734-170">Om du vill skapa en ny rollgrupp manuellt använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="ab734-171">Parametern _Roller_ anger vilka hanteringsroller som ska tilldelas rollgruppen med hjälp av följande syntax `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="ab734-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="ab734-172">Du kan se tillgängliga roller med hjälp av **Cmdlet Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="ab734-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="ab734-173">Parametern _Medlemmar_ anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="ab734-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="ab734-174">Du kan ange användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).</span><span class="sxs-lookup"><span data-stu-id="ab734-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="ab734-175">I det här exemplet skapas en ny rollgrupp med namnet "Begränsad mottagarehantering" med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ab734-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="ab734-176">Rollen Mottagare av e-post tilldelas rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="ab734-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="ab734-177">Användarna Kim och Martin läggs till som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ab734-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="ab734-178">Så här kopierar du en befintlig rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="ab734-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="ab734-179">Lagra den rollgrupp som du vill kopiera i en variabel med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="ab734-180">Skapa den nya rollgruppen med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="ab734-181">Parametern _Medlemmar_ anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="ab734-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="ab734-182">Du kan ange användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).</span><span class="sxs-lookup"><span data-stu-id="ab734-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="ab734-183">I det här exemplet kopieras rollgruppen Organisationshantering till den nya rollgruppen "Begränsad organisationshantering".</span><span class="sxs-lookup"><span data-stu-id="ab734-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="ab734-184">Rollgruppmedlemmarna är Isabelle, Carter och Lukas.</span><span class="sxs-lookup"><span data-stu-id="ab734-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="ab734-185">Detaljerad syntax- och parameterinformation, [Nyrollgrupp](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="ab734-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="ab734-186">Använda fristående EOP PowerShell ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="ab734-187">Cmdlets **för Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar en i taget.</span><span class="sxs-lookup"><span data-stu-id="ab734-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="ab734-188">**Cmdlet för Update-RoleGroupMember** kan ersätta eller ändra den befintliga medlemslistan.</span><span class="sxs-lookup"><span data-stu-id="ab734-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="ab734-189">Medlemmarna i en rollgrupp kan vara användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).</span><span class="sxs-lookup"><span data-stu-id="ab734-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="ab734-190">Om du vill ändra medlemmarna i en rollgrupp använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="ab734-191">Om du vill _ersätta_ den befintliga medlemslistan med de värden du anger använder du följande syntax: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="ab734-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="ab734-192">Om du vill ändra den befintliga medlemslistan _selektivt_ använder du följande syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="ab734-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="ab734-193">Det här exemplet ersätter alla aktuella medlemmar i rollgruppen Help Desk med de angivna användarna.</span><span class="sxs-lookup"><span data-stu-id="ab734-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="ab734-194">I det här exemplet läggs Daigoro Akai till och Valeria Barrio tas bort från listan över medlemmar i rollgruppen Help Desk.</span><span class="sxs-lookup"><span data-stu-id="ab734-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="ab734-195">Detaljerad syntax- och parameterinformation finns i [Uppdatera rollgruppmedlem](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="ab734-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="ab734-196">Använd fristående EOP PowerShell för att ta bort rollgrupper</span><span class="sxs-lookup"><span data-stu-id="ab734-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="ab734-197">Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="ab734-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="ab734-198">Om du vill ta bort en anpassad rollgrupp använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ab734-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="ab734-199">I det här exemplet tas rollgruppen Utbildningsadministratörer bort.</span><span class="sxs-lookup"><span data-stu-id="ab734-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="ab734-200">Detaljerad syntax- och parameterinformation finns i [Ta bort rollgrupp](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="ab734-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ab734-201">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="ab734-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="ab734-202">Så här kontrollerar du att du har kopierat en rollgrupp:</span><span class="sxs-lookup"><span data-stu-id="ab734-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="ab734-203">Gå till **Behörighetsadministratörsroller** i EAC och kontrollera att \> **Admin roles**rollgruppen visas (eller inte visas).</span><span class="sxs-lookup"><span data-stu-id="ab734-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="ab734-204">Markera rollgruppen och kontrollera inställningarna i informationsfönstret eller klicka på **Redigera** ![ redigera ikon för att verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ab734-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="ab734-205">I Exchange Online PowerShell ersätter du \< Rollgruppsnamnet \> med namnet på rollgruppen och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ab734-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
