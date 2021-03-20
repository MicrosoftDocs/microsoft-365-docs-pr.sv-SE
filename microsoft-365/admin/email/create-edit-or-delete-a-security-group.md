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
ms.openlocfilehash: d2cc749acaf7b2e23674156f6ad9a200ec7b386d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915824"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="68650-103">Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68650-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="68650-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="68650-104">The admin center is changing.</span></span> <span data-ttu-id="68650-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="68650-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="68650-106">På sidan Microsoft 365 **Grupper** kan du skapa grupper med användarkonton som du kan använda för att tilldela samma behörigheter för SharePoint Online och CRM Online.</span><span class="sxs-lookup"><span data-stu-id="68650-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="68650-107">En administratör kan till exempel skapa en säkerhetsgrupp för att bevilja en viss grupp personer åtkomst till en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="68650-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="68650-108">Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="68650-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="68650-109">Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="68650-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="68650-110">Planerar du att använda webbplatspostlådor?</span><span class="sxs-lookup"><span data-stu-id="68650-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="68650-111">Alla användare som läggs till på en SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan endast använda webbplatspostlådan från SharePoint.</span><span class="sxs-lookup"><span data-stu-id="68650-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="68650-112">De här användarna kan inte komma åt webbplatspostlådan från Outlook.</span><span class="sxs-lookup"><span data-stu-id="68650-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="68650-113">Mer information finns i Använda [Microsoft 365-grupper i stället för webbplatspostlådor.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="68650-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="68650-114">Hantera säkerhetsgrupper i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="68650-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="68650-115">Lägga till en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="68650-115">Add a security group</span></span>

1. <span data-ttu-id="68650-116">Gå till sidan Grupper grupper i administrationscentret för Microsoft 365.  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="68650-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="68650-117">Välj Lägg **till** en grupp **på sidan Grupper.**</span><span class="sxs-lookup"><span data-stu-id="68650-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="68650-118">På sidan **Välj en grupptyp** väljer du **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="68650-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="68650-119">Följ anvisningarna för att slutföra skapandet av gruppen.</span><span class="sxs-lookup"><span data-stu-id="68650-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="68650-120">Lägga till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="68650-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="68650-121">Välj namnet på säkerhetsgruppen på **sidan Grupper** och välj **Visa** alla och hantera medlemmar på **fliken Medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="68650-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="68650-122">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="68650-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="68650-123">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="68650-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="68650-124">Välj namnet på säkerhetsgruppen på **sidan** Grupper och välj sedan **Redigera** bredvid **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="68650-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="68650-125">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="68650-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="68650-126">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="68650-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="68650-127">Välj namnet på säkerhetsgruppen på **sidan** Grupper och välj sedan **Redigera** bredvid **Medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="68650-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="68650-128">Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="68650-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="68650-129">Om du vill ta bort medlemmar väljer du X bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="68650-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="68650-130">Redigera en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="68650-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="68650-131">Gå till sidan Grupper i **administrationscentret.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="68650-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="68650-132">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="68650-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="68650-133">I inställningsfönstret väljer du fliken **Allmänt eller** Fliken Medlemmar **för att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="68650-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="68650-134">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">sidan Grupper</a>i  \>  administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="68650-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="68650-135">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="68650-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="68650-136">I fönstret säkerhetsgrupp väljer du Redigera **bredvid fliken** Namn eller Medlemmar **för** **att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="68650-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="68650-137">När du har gjort ändringar väljer du **Spara** \> **stäng.**</span><span class="sxs-lookup"><span data-stu-id="68650-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="68650-138">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">sidan Grupper</a>i  \>  administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="68650-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="68650-139">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="68650-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="68650-140">I fönstret säkerhetsgrupp väljer du Redigera **bredvid fliken** Namn eller Medlemmar **för** **att** redigera antingen gruppinformation eller medlemmar.</span><span class="sxs-lookup"><span data-stu-id="68650-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="68650-141">När du har gjort ändringar väljer du **Spara** > **stäng.**</span><span class="sxs-lookup"><span data-stu-id="68650-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="68650-142">Ta bort en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="68650-142">Delete a security group</span></span>

1. <span data-ttu-id="68650-143">Gå till sidan Grupper i **administrationscentret.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="68650-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="68650-144">Markera **gruppens** namn på sidan Grupper.</span><span class="sxs-lookup"><span data-stu-id="68650-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="68650-145">Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="68650-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="68650-146">Välj **Stäng** när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="68650-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="68650-147">Grupper i Exchange Online och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68650-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="68650-148">Om du vill skapa grupper med användare så att du kan skicka e-post till dem samtidigt  kan du göra det i administrationscentret för Exchange genom att gå till Administratörsgrupper \> för mottagare i  \>  \> Exchange.</span><span class="sxs-lookup"><span data-stu-id="68650-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="68650-149">Välj sedan **Ny** ![ lägg till och välj den typ av grupp du ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) vill skapa:</span><span class="sxs-lookup"><span data-stu-id="68650-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="68650-150">**Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="68650-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="68650-151">Det kallas även för en *e-postaktiverad distributionsgrupp* eller en *distributionslista.*</span><span class="sxs-lookup"><span data-stu-id="68650-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="68650-152">Mer information finns i [Hantera distributionsgrupper](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="68650-152">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="68650-153">**Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser.</span><span class="sxs-lookup"><span data-stu-id="68650-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="68650-154">Den här gruppen kallas även för *en e-postaktiverad säkerhetsgrupp.*</span><span class="sxs-lookup"><span data-stu-id="68650-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="68650-155">Mer information finns i Hantera [e-postaktiverade säkerhetsgrupper.](/Exchange/recipients/mail-enabled-security-groups)</span><span class="sxs-lookup"><span data-stu-id="68650-155">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="68650-156">**Dynamisk distributionsgrupp:** En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du anger.</span><span class="sxs-lookup"><span data-stu-id="68650-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="68650-157">Mer information finns i [Hantera dynamiska distributionsgrupper.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="68650-157">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="68650-158">När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange visas deras namn och användarlistor på **sidan Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="68650-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="68650-159">Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="68650-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="68650-160">Dynamiska distributionsgrupper visas inte på sidan **Säkerhetsgrupper.**</span><span class="sxs-lookup"><span data-stu-id="68650-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="68650-161">SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="68650-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="68650-162">De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller.</span><span class="sxs-lookup"><span data-stu-id="68650-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="68650-163">Mer information finns i [Förinställda SharePoint-grupper i SharePoint Online.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="68650-163">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="68650-164">Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?</span><span class="sxs-lookup"><span data-stu-id="68650-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="68650-165">Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med flera.</span><span class="sxs-lookup"><span data-stu-id="68650-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="68650-166">En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="68650-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="68650-167">Måste jag använda säkerhetsgrupper för min organisation för att vara säker?</span><span class="sxs-lookup"><span data-stu-id="68650-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="68650-p111">Nej. Det här är ett annat sätt som du kan hantera säkerhet för din organisation. Du kan alltid bevilja användarbehörigheter och åtkomst till webbplatser individuellt. Men med säkerhetsgrupper kan du enkelt hantera större grupper med användare.</span><span class="sxs-lookup"><span data-stu-id="68650-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="68650-172">Kan jag skicka e-post till en säkerhetsgrupp?</span><span class="sxs-lookup"><span data-stu-id="68650-172">Can I send email to a security group?</span></span>

<span data-ttu-id="68650-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="68650-173">Yes.</span></span> <span data-ttu-id="68650-174">Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Microsoft 365-grupp i](../create-groups/create-groups.md) stället.</span><span class="sxs-lookup"><span data-stu-id="68650-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
