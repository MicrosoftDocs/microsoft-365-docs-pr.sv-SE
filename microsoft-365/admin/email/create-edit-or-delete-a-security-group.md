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
ms.openlocfilehash: f51c21261a83e1a0034a67f9f1580dd297a3d583
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808033"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b829b-103">Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b829b-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b829b-104">På sidan Grupper **i** Office 365 kan du skapa grupper av användarkonton som du kan använda för att tilldela samma behörigheter till i SharePoint Online och CRM Online.</span><span class="sxs-lookup"><span data-stu-id="b829b-104">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="b829b-105">En administratör kan till exempel skapa en säkerhetsgrupp för att ge en viss grupp personer åtkomst till en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="b829b-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="b829b-106">Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b829b-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="b829b-107">Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="b829b-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b829b-108">Planerar du att använda webbplatspostlådor?</span><span class="sxs-lookup"><span data-stu-id="b829b-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="b829b-109">Alla användare som läggs till på en SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan bara använda webbplatspostlådan från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b829b-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="b829b-110">Dessa användare kan inte komma åt webbplatspostlådan från Outlook.</span><span class="sxs-lookup"><span data-stu-id="b829b-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="b829b-111">Mer information finns i [Använda Office 365-grupper i stället för Webbplatspostlådor](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="b829b-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="b829b-112">Hantera säkerhetsgrupper i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="b829b-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="b829b-113">Lägga till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b829b-113">Add a security group</span></span>

1. <span data-ttu-id="b829b-114">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b829b-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b829b-115">På sidan **Grupper** väljer du **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="b829b-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="b829b-116">Välj **Säkerhet**på sidan **Välj grupptyp** .</span><span class="sxs-lookup"><span data-stu-id="b829b-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="b829b-117">Följ stegen för att slutföra skapandet av gruppen.</span><span class="sxs-lookup"><span data-stu-id="b829b-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="b829b-118">Lägga till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b829b-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b829b-119">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="b829b-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="b829b-120">Välj säkerhetsgruppsnamnet på sidan **Grupper** och välj **Visa alla och hantera medlemmar**på fliken **Medlemmar** .</span><span class="sxs-lookup"><span data-stu-id="b829b-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="b829b-121">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="b829b-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b829b-122">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="b829b-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b829b-123">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="b829b-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b829b-124">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="b829b-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b829b-125">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="b829b-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="b829b-126">Markera säkerhetsgruppsnamnet på sidan **Grupper** och välj sedan **Redigera bredvid** **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="b829b-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b829b-127">I gruppfönstret väljer du **Lägg till medlemmar** och väljer personen i listan eller skriver namnet på den person som du vill lägga till i sökrutan och väljer sedan **Spara**. **Search**</span><span class="sxs-lookup"><span data-stu-id="b829b-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b829b-128">Om du vill ta bort medlemmar markerar du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="b829b-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="b829b-129">Redigera en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b829b-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b829b-130">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="b829b-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="b829b-131">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b829b-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b829b-132">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="b829b-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b829b-133">I inställningsfönstret väljer du fliken **Allmänt** eller fliken **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="b829b-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b829b-134">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b829b-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b829b-135">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="b829b-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b829b-136">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="b829b-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b829b-137">När du har gjort ändringar väljer du **Spara** \> **nära**.</span><span class="sxs-lookup"><span data-stu-id="b829b-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b829b-138">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b829b-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b829b-139">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="b829b-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b829b-140">I säkerhetsgruppsfönstret väljer du **Redigera bredvid** fliken **Namn** eller **Medlemmar** om du vill redigera gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="b829b-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b829b-141">När du har gjort ändringar väljer du **Spara** \> **nära**.</span><span class="sxs-lookup"><span data-stu-id="b829b-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="b829b-142">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b829b-142">Delete a security group</span></span>

1. <span data-ttu-id="b829b-143">Gå till sidan **Gruppergrupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b829b-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="b829b-144">Välj gruppens namn på sidan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="b829b-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b829b-145">Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="b829b-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="b829b-146">Välj **Stäng** när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="b829b-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="b829b-147">Grupper i Exchange Online och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b829b-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="b829b-148">Om du vill skapa grupper av användare så att du kan skicka e-post till dem alla samtidigt kan du göra det i administrationscentret för Exchange genom att \> gå till **Admin** \> **Administratörsutbytesmottagare** \> **Recipients** grupper . **Groups**</span><span class="sxs-lookup"><span data-stu-id="b829b-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="b829b-149">Välj sedan **New**![Nytt](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)lägg till och välj den typ av grupp som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="b829b-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="b829b-150">**Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="b829b-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="b829b-151">Det kallas också en *e-postaktiverad distributionsgrupp*eller, i Office 365, en *distributionslista*.</span><span class="sxs-lookup"><span data-stu-id="b829b-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="b829b-152">Mer information finns i [Hantera distributionsgrupper](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="b829b-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="b829b-153">**Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser.</span><span class="sxs-lookup"><span data-stu-id="b829b-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="b829b-154">Den här gruppen kallas också för en *e-postaktiverad säkerhetsgrupp*.</span><span class="sxs-lookup"><span data-stu-id="b829b-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="b829b-155">Mer information finns i [Hantera e-postaktiverade säkerhetsgrupper](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="b829b-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="b829b-156">**Dynamisk distributionsgrupp**: En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du definierar.</span><span class="sxs-lookup"><span data-stu-id="b829b-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="b829b-157">Mer information finns i [Hantera dynamiska distributionsgrupper](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="b829b-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="b829b-p107">När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange visas gruppnamnen och användarlistorna på sidan **Säkerhetsgrupper** i Office 365. Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange. Dynamiska distributionslistor visas inte på sidan **Säkerhetsgrupper** i Office 365.</span><span class="sxs-lookup"><span data-stu-id="b829b-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="b829b-161">SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="b829b-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="b829b-162">De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller.</span><span class="sxs-lookup"><span data-stu-id="b829b-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="b829b-163">Mer information finns [i Standard-SharePoint-grupper i SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span><span class="sxs-lookup"><span data-stu-id="b829b-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="b829b-164">Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?</span><span class="sxs-lookup"><span data-stu-id="b829b-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="b829b-165">Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med mera.</span><span class="sxs-lookup"><span data-stu-id="b829b-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="b829b-166">En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="b829b-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="b829b-167">Måste jag använda säkerhetsgrupper för att min organisation ska vara säker?</span><span class="sxs-lookup"><span data-stu-id="b829b-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="b829b-p110">Nej. Det här är ett annat sätt som du kan hantera säkerhet för din organisation. Du kan alltid bevilja användarbehörigheter och åtkomst till webbplatser individuellt. Men med säkerhetsgrupper kan du enkelt hantera större grupper med användare.</span><span class="sxs-lookup"><span data-stu-id="b829b-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="b829b-172">Kan jag skicka e-post till en säkerhetsgrupp?</span><span class="sxs-lookup"><span data-stu-id="b829b-172">Can I send email to a security group?</span></span>

<span data-ttu-id="b829b-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="b829b-173">Yes.</span></span> <span data-ttu-id="b829b-174">Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Office 365-grupp](../create-groups/create-groups.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="b829b-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
