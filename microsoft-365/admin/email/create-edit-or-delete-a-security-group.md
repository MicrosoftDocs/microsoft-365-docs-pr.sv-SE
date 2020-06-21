---
title: Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Lär dig att skapa, redigera eller ta bort en säkerhetsgrupp.
ms.openlocfilehash: c7c8d57037d972cd89dad45358dc5a7aa3fb86e8
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780247"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="63fea-103">Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63fea-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="63fea-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="63fea-104">The admin center is changing.</span></span> <span data-ttu-id="63fea-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="63fea-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="63fea-106">På sidan Microsoft 365 **Groups** kan du skapa grupper av användarkonton som du kan använda för att tilldela samma behörigheter till i SharePoint Online och CRM Online.</span><span class="sxs-lookup"><span data-stu-id="63fea-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="63fea-107">En administratör kan till exempel skapa en säkerhetsgrupp för att ge en viss grupp personer åtkomst till en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="63fea-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="63fea-108">Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="63fea-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="63fea-109">Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="63fea-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="63fea-110">Planerar du att använda webbplatspostlådor?</span><span class="sxs-lookup"><span data-stu-id="63fea-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="63fea-111">Alla användare som läggs till på en SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan bara använda webbplatspostlådan från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="63fea-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="63fea-112">Dessa användare kan inte komma åt webbplatspostlådan från Outlook.</span><span class="sxs-lookup"><span data-stu-id="63fea-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="63fea-113">Mer information finns i [Använda Microsoft 365 Grupper i stället för Webbplatspostlådor](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="63fea-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="63fea-114">Hantera säkerhetsgrupper i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="63fea-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="63fea-115">Lägga till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="63fea-115">Add a security group</span></span>

1. <span data-ttu-id="63fea-116">Gå till sidan Gruppergrupper i **administrationscentret för**Microsoft 365.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a></span><span class="sxs-lookup"><span data-stu-id="63fea-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="63fea-117">På sidan **Grupper** väljer du **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="63fea-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="63fea-118">Välj **Säkerhet**på sidan **Välj grupptyp** .</span><span class="sxs-lookup"><span data-stu-id="63fea-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="63fea-119">Följ stegen för att slutföra skapandet av gruppen.</span><span class="sxs-lookup"><span data-stu-id="63fea-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="63fea-120">Lägga till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="63fea-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="63fea-121">Välj säkerhetsgruppsnamnet på sidan **Grupper** och välj **Visa alla och hantera medlemmar**på fliken **Medlemmar** .</span><span class="sxs-lookup"><span data-stu-id="63fea-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="63fea-122">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="63fea-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="63fea-123">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="63fea-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="63fea-124">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="63fea-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="63fea-125">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="63fea-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="63fea-126">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="63fea-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="63fea-127">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="63fea-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="63fea-128">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="63fea-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="63fea-129">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="63fea-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="63fea-130">Redigera en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="63fea-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="63fea-131">Gå till sidan **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppergrupper i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="63fea-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="63fea-132">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="63fea-133">I inställningsfönstret väljer du fliken **Allmänt** eller fliken **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="63fea-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="63fea-134">Gå till sidan **Gruppergrupper** i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> \> **Groups**</span><span class="sxs-lookup"><span data-stu-id="63fea-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="63fea-135">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="63fea-136">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="63fea-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="63fea-137">När du har gjort ändringar väljer du **Spara** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="63fea-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="63fea-138">Gå till sidan **Gruppergrupper** i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> \> **Groups**</span><span class="sxs-lookup"><span data-stu-id="63fea-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="63fea-139">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="63fea-140">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="63fea-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="63fea-141">När du har gjort ändringar väljer du **Spara** > **stäng**.</span><span class="sxs-lookup"><span data-stu-id="63fea-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="63fea-142">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="63fea-142">Delete a security group</span></span>

1. <span data-ttu-id="63fea-143">Gå till sidan **Groups**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppergrupper i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="63fea-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="63fea-144">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="63fea-145">Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="63fea-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="63fea-146">Välj **Stäng** när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="63fea-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="63fea-147">Grupper i Exchange Online och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="63fea-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="63fea-148">Om du vill skapa grupper av användare så att du kan skicka e-post till dem alla samtidigt kan du göra det i administrationscentret för Exchange genom att gå till **Administratör** \> **Exchange** \> **Exchange-mottagare** \> **grupper**.</span><span class="sxs-lookup"><span data-stu-id="63fea-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="63fea-149">Välj sedan **Nytt** ![ tillägg och välj den typ av grupp som du ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) vill skapa:</span><span class="sxs-lookup"><span data-stu-id="63fea-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="63fea-150">**Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="63fea-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="63fea-151">Det kallas också en *e-postaktiverad distributionsgrupp*eller en *distributionslista*.</span><span class="sxs-lookup"><span data-stu-id="63fea-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="63fea-152">Mer information finns i [Hantera distributionsgrupper](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="63fea-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="63fea-153">**Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser.</span><span class="sxs-lookup"><span data-stu-id="63fea-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="63fea-154">Den här gruppen kallas också för en *e-postaktiverad säkerhetsgrupp*.</span><span class="sxs-lookup"><span data-stu-id="63fea-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="63fea-155">Mer information finns i [Hantera e-postaktiverade säkerhetsgrupper](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="63fea-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="63fea-156">**Dynamisk distributionsgrupp**: En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du definierar.</span><span class="sxs-lookup"><span data-stu-id="63fea-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="63fea-157">Mer information finns i [Hantera dynamiska distributionsgrupper](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="63fea-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="63fea-158">När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange visas deras namn och användarlistor på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="63fea-159">Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="63fea-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="63fea-160">Dynamiska distributionsgrupper visas inte på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="63fea-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="63fea-161">SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="63fea-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="63fea-162">De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller.</span><span class="sxs-lookup"><span data-stu-id="63fea-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="63fea-163">Mer information finns [i Standard-SharePoint-grupper i SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="63fea-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="63fea-164">Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?</span><span class="sxs-lookup"><span data-stu-id="63fea-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="63fea-165">Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med mera.</span><span class="sxs-lookup"><span data-stu-id="63fea-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="63fea-166">En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="63fea-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="63fea-167">Måste jag använda säkerhetsgrupper för att min organisation ska vara säker?</span><span class="sxs-lookup"><span data-stu-id="63fea-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="63fea-168">No.</span><span class="sxs-lookup"><span data-stu-id="63fea-168">No.</span></span> <span data-ttu-id="63fea-169">This is just one more way you can manage security for your organization.</span><span class="sxs-lookup"><span data-stu-id="63fea-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="63fea-170">You can always grant user permissions and access to sites individually.</span><span class="sxs-lookup"><span data-stu-id="63fea-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="63fea-171">But with security groups, you can easily manage larger groups of users.</span><span class="sxs-lookup"><span data-stu-id="63fea-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="63fea-172">Kan jag skicka e-post till en säkerhetsgrupp?</span><span class="sxs-lookup"><span data-stu-id="63fea-172">Can I send email to a security group?</span></span>

<span data-ttu-id="63fea-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="63fea-173">Yes.</span></span> <span data-ttu-id="63fea-174">Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Microsoft 365-grupp](../create-groups/create-groups.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="63fea-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
