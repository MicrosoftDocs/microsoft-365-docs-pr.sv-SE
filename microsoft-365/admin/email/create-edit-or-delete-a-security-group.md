---
title: Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579344"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3e794-103">Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e794-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3e794-104">På sidan Microsoft 365 **Grupper** kan du skapa grupper med användarkonton som du kan använda för att tilldela samma behörigheter för SharePoint Online och CRM Online.</span><span class="sxs-lookup"><span data-stu-id="3e794-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="3e794-105">En administratör kan till exempel skapa en säkerhetsgrupp för att bevilja en viss grupp personer åtkomst till en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="3e794-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="3e794-106">Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3e794-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="3e794-107">Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="3e794-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="3e794-108">Planerar du att använda webbplatspostlådor?</span><span class="sxs-lookup"><span data-stu-id="3e794-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="3e794-109">Alla användare som läggs till på en SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan endast använda webbplatspostlådan från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3e794-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="3e794-110">De här användarna kan inte komma åt webbplatspostlådan från Outlook.</span><span class="sxs-lookup"><span data-stu-id="3e794-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="3e794-111">Mer information finns i Använda [Microsoft 365-grupper i stället för webbplatspostlådor.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="3e794-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="3e794-112">Hantera säkerhetsgrupper i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="3e794-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="3e794-113">Lägga till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="3e794-113">Add a security group</span></span>

1. <span data-ttu-id="3e794-114">Gå till sidan Grupper grupper i administrationscentret för Microsoft 365.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="3e794-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="3e794-115">Välj Lägg **till** en grupp **på sidan Grupper.**</span><span class="sxs-lookup"><span data-stu-id="3e794-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="3e794-116">På sidan **Välj en grupptyp** väljer du **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="3e794-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="3e794-117">Följ anvisningarna för att slutföra skapandet av gruppen.</span><span class="sxs-lookup"><span data-stu-id="3e794-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="3e794-118">Lägga till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="3e794-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="3e794-119">Välj namnet på säkerhetsgruppen på **sidan Grupper** och välj **Visa** alla och hantera medlemmar på **fliken Medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="3e794-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="3e794-120">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e794-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="3e794-121">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="3e794-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3e794-122">Välj namnet på säkerhetsgruppen på **sidan** Grupper och välj sedan **Redigera** bredvid **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="3e794-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="3e794-123">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e794-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="3e794-124">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="3e794-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="3e794-125">Välj namnet på säkerhetsgruppen på **sidan** Grupper och välj sedan **Redigera** bredvid **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="3e794-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="3e794-126">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e794-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="3e794-127">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="3e794-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="3e794-128">Redigera en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="3e794-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3e794-129">Gå till sidan Grupper i **administrationscentret.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="3e794-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="3e794-130">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="3e794-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="3e794-131">I inställningsfönstret väljer du fliken **Allmänt eller** Fliken Medlemmar **för att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3e794-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3e794-132">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">sidan Grupper</a>i  \>  administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3e794-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="3e794-133">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="3e794-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="3e794-134">I fönstret säkerhetsgrupp väljer du Redigera **bredvid fliken** Namn eller Medlemmar **för** **att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3e794-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="3e794-135">När du har gjort ändringar väljer du **Spara** \> **stäng.**</span><span class="sxs-lookup"><span data-stu-id="3e794-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3e794-136">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">sidan Grupper</a>i  \>  administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3e794-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="3e794-137">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="3e794-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="3e794-138">I fönstret säkerhetsgrupp väljer du Redigera **bredvid fliken** Namn eller Medlemmar **för** **att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3e794-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="3e794-139">När du har gjort ändringar väljer du **Spara** > **stäng.**</span><span class="sxs-lookup"><span data-stu-id="3e794-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="3e794-140">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="3e794-140">Delete a security group</span></span>

1. <span data-ttu-id="3e794-141">Gå till sidan Grupper i **administrationscentret.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="3e794-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="3e794-142">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="3e794-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="3e794-143">Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="3e794-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="3e794-144">Välj **Stäng** när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="3e794-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="3e794-145">Grupper i Exchange Online och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3e794-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="3e794-146">Om du vill skapa grupper med användare så att du kan skicka e-post till dem samtidigt  kan du göra det i administrationscentret för Exchange genom att gå till Administratörsgrupper \> för mottagare i  \>  \> Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e794-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="3e794-147">Välj sedan **Ny** ![ lägg till och välj den typ av grupp du ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) vill skapa:</span><span class="sxs-lookup"><span data-stu-id="3e794-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="3e794-148">**Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="3e794-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="3e794-149">Det kallas även för en *e-postaktiverad distributionsgrupp* eller en *distributionslista.*</span><span class="sxs-lookup"><span data-stu-id="3e794-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="3e794-150">Mer information finns i [Hantera distributionsgrupper](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="3e794-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="3e794-151">**Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser.</span><span class="sxs-lookup"><span data-stu-id="3e794-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="3e794-152">Den här gruppen kallas även för *en e-postaktiverad säkerhetsgrupp.*</span><span class="sxs-lookup"><span data-stu-id="3e794-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="3e794-153">Mer information finns i Hantera [e-postaktiverade säkerhetsgrupper.](/Exchange/recipients/mail-enabled-security-groups)</span><span class="sxs-lookup"><span data-stu-id="3e794-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="3e794-154">**Dynamisk distributionsgrupp:** En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du anger.</span><span class="sxs-lookup"><span data-stu-id="3e794-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="3e794-155">Mer information finns i [Hantera dynamiska distributionsgrupper.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="3e794-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="3e794-156">När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange visas deras namn och användarlistor på **sidan Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="3e794-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="3e794-157">Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e794-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="3e794-158">Dynamiska distributionsgrupper visas inte på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="3e794-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="3e794-159">SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="3e794-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="3e794-160">De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller.</span><span class="sxs-lookup"><span data-stu-id="3e794-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="3e794-161">Mer information finns i [Förinställda SharePoint-grupper i SharePoint Online.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="3e794-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="3e794-162">Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?</span><span class="sxs-lookup"><span data-stu-id="3e794-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="3e794-163">Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med flera.</span><span class="sxs-lookup"><span data-stu-id="3e794-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="3e794-164">En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="3e794-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="3e794-165">Måste jag använda säkerhetsgrupper för min organisation för att vara säker?</span><span class="sxs-lookup"><span data-stu-id="3e794-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="3e794-p110">Nej. Det här är ett annat sätt som du kan hantera säkerhet för din organisation. Du kan alltid bevilja användarbehörigheter och åtkomst till webbplatser individuellt. Men med säkerhetsgrupper kan du enkelt hantera större grupper med användare.</span><span class="sxs-lookup"><span data-stu-id="3e794-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="3e794-170">Kan jag skicka e-post till en säkerhetsgrupp?</span><span class="sxs-lookup"><span data-stu-id="3e794-170">Can I send email to a security group?</span></span>

<span data-ttu-id="3e794-171">Ja.</span><span class="sxs-lookup"><span data-stu-id="3e794-171">Yes.</span></span> <span data-ttu-id="3e794-172">Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Microsoft 365-grupp i](../create-groups/create-groups.md) stället.</span><span class="sxs-lookup"><span data-stu-id="3e794-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
