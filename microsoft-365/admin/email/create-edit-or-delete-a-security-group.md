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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Lär dig att skapa, redigera eller ta bort en säkerhetsgrupp.
ms.openlocfilehash: 6f4daa66c11675674fdbfbfeb625128d8f817520
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140447"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="faab4-103">Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="faab4-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="faab4-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="faab4-104">The admin center is changing.</span></span> <span data-ttu-id="faab4-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="faab4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="faab4-106">På sidan Microsoft 365 **Groups** kan du skapa grupper av användarkonton som du kan använda för att tilldela samma behörigheter till i SharePoint Online och CRM Online.</span><span class="sxs-lookup"><span data-stu-id="faab4-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="faab4-107">En administratör kan till exempel skapa en säkerhetsgrupp för att ge en viss grupp personer åtkomst till en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="faab4-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="faab4-108">Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="faab4-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="faab4-109">Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="faab4-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="faab4-110">Planerar du att använda webbplatspostlådor?</span><span class="sxs-lookup"><span data-stu-id="faab4-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="faab4-111">Alla användare som läggs till på en SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan bara använda webbplatspostlådan från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="faab4-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="faab4-112">Dessa användare kan inte komma åt webbplatspostlådan från Outlook.</span><span class="sxs-lookup"><span data-stu-id="faab4-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="faab4-113">Mer information finns i [Använda Microsoft 365-grupper i stället för Webbplatspostlådor](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="faab4-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="faab4-114">Hantera säkerhetsgrupper i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="faab4-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="faab4-115">Lägga till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="faab4-115">Add a security group</span></span>

1. <span data-ttu-id="faab4-116">Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppergrupper i</a> **administrationscentret för** > Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="faab4-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="faab4-117">På sidan **Grupper** väljer du **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="faab4-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="faab4-118">Välj **Säkerhet**på sidan **Välj grupptyp** .</span><span class="sxs-lookup"><span data-stu-id="faab4-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="faab4-119">Följ stegen för att slutföra skapandet av gruppen.</span><span class="sxs-lookup"><span data-stu-id="faab4-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="faab4-120">Lägga till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="faab4-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="faab4-121">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="faab4-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="faab4-122">Välj säkerhetsgruppsnamnet på sidan **Grupper** och välj **Visa alla och hantera medlemmar**på fliken **Medlemmar** .</span><span class="sxs-lookup"><span data-stu-id="faab4-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="faab4-123">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="faab4-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="faab4-124">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="faab4-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="faab4-125">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="faab4-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="faab4-126">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="faab4-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="faab4-127">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="faab4-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="faab4-128">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="faab4-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="faab4-129">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="faab4-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="faab4-130">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="faab4-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="faab4-131">Redigera en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="faab4-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="faab4-132">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="faab4-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="faab4-133">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="faab4-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="faab4-134">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="faab4-135">I inställningsfönstret väljer du fliken **Allmänt** eller fliken **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="faab4-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="faab4-136">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="faab4-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="faab4-137">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="faab4-138">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="faab4-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="faab4-139">När du har gjort ändringar väljer du **Spara** \> **nära**.</span><span class="sxs-lookup"><span data-stu-id="faab4-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="faab4-140">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="faab4-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="faab4-141">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="faab4-142">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="faab4-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="faab4-143">När du har gjort ändringar väljer du **Spara** > **nära**.</span><span class="sxs-lookup"><span data-stu-id="faab4-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="faab4-144">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="faab4-144">Delete a security group</span></span>

1. <span data-ttu-id="faab4-145">Gå till sidan **Gruppergrupper** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="faab4-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="faab4-146">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="faab4-147">Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="faab4-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="faab4-148">Välj **Stäng** när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="faab4-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="faab4-149">Grupper i Exchange Online och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="faab4-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="faab4-150">Om du vill skapa grupper av användare så att du kan skicka e-post till dem alla samtidigt kan du göra det i administrationscentret för Exchange genom att \> gå till **Admin** \> **Administratörsutbytesmottagare** \> **Recipients** grupper . **Groups**</span><span class="sxs-lookup"><span data-stu-id="faab4-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="faab4-151">Välj sedan **New**![Nytt](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)lägg till och välj den typ av grupp som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="faab4-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="faab4-152">**Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="faab4-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="faab4-153">Det kallas också en *e-postaktiverad distributionsgrupp*eller en *distributionslista*.</span><span class="sxs-lookup"><span data-stu-id="faab4-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="faab4-154">Mer information finns i [Hantera distributionsgrupper](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="faab4-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="faab4-155">**Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser.</span><span class="sxs-lookup"><span data-stu-id="faab4-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="faab4-156">Den här gruppen kallas också för en *e-postaktiverad säkerhetsgrupp*.</span><span class="sxs-lookup"><span data-stu-id="faab4-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="faab4-157">Mer information finns i [Hantera e-postaktiverade säkerhetsgrupper](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="faab4-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="faab4-158">**Dynamisk distributionsgrupp**: En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du definierar.</span><span class="sxs-lookup"><span data-stu-id="faab4-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="faab4-159">Mer information finns i [Hantera dynamiska distributionsgrupper](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="faab4-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="faab4-160">När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange visas deras namn och användarlistor på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="faab4-161">Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="faab4-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="faab4-162">Dynamiska distributionsgrupper visas inte på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="faab4-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="faab4-163">SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="faab4-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="faab4-164">De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller.</span><span class="sxs-lookup"><span data-stu-id="faab4-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="faab4-165">Mer information finns [i Standard-SharePoint-grupper i SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="faab4-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="faab4-166">Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?</span><span class="sxs-lookup"><span data-stu-id="faab4-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="faab4-167">Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med mera.</span><span class="sxs-lookup"><span data-stu-id="faab4-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="faab4-168">En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="faab4-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="faab4-169">Måste jag använda säkerhetsgrupper för att min organisation ska vara säker?</span><span class="sxs-lookup"><span data-stu-id="faab4-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="faab4-p111">Nej. Det här är ett annat sätt som du kan hantera säkerhet för din organisation. Du kan alltid bevilja användarbehörigheter och åtkomst till webbplatser individuellt. Men med säkerhetsgrupper kan du enkelt hantera större grupper med användare.</span><span class="sxs-lookup"><span data-stu-id="faab4-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="faab4-174">Kan jag skicka e-post till en säkerhetsgrupp?</span><span class="sxs-lookup"><span data-stu-id="faab4-174">Can I send email to a security group?</span></span>

<span data-ttu-id="faab4-175">Ja.</span><span class="sxs-lookup"><span data-stu-id="faab4-175">Yes.</span></span> <span data-ttu-id="faab4-176">Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Microsoft 365-grupp](../create-groups/create-groups.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="faab4-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
