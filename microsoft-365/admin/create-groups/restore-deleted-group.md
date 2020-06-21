---
title: Återställa en borttagen grupp
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818513"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="1e8ed-103">Återställa en borttagen grupp</span><span class="sxs-lookup"><span data-stu-id="1e8ed-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e8ed-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-104">The admin center is changing.</span></span> <span data-ttu-id="1e8ed-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1e8ed-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1e8ed-106">Om du har tagit bort en grupp behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="1e8ed-107">Den här 30-dagarsperioden anses vara en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="1e8ed-108">Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="1e8ed-109">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="1e8ed-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="1e8ed-110">Azure Active Directory (AD) Microsoft 365 Grupper objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="1e8ed-111">gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="1e8ed-112">Exchange Online delad inkorg och kalender.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="1e8ed-113">SharePoint Online-gruppwebbplats och -filer.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="1e8ed-114">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="1e8ed-114">OneNote notebook</span></span>
    
- <span data-ttu-id="1e8ed-115">Planner</span><span class="sxs-lookup"><span data-stu-id="1e8ed-115">Planner</span></span>
    
- <span data-ttu-id="1e8ed-116">Teams</span><span class="sxs-lookup"><span data-stu-id="1e8ed-116">Teams</span></span>

- <span data-ttu-id="1e8ed-117">Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="1e8ed-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="1e8ed-118">Återställa en grupp som du äger med Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="1e8ed-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="1e8ed-119">Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="1e8ed-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="1e8ed-120">På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="1e8ed-121">Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="1e8ed-122">Om den borttagna gruppen inte visas här kontaktar du en administratör.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1e8ed-123">Återställa en grupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e8ed-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1e8ed-124">Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i microsoft 365-administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="1e8ed-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="1e8ed-125">Gå till [administrationscentret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1e8ed-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="1e8ed-126">Expandera **grupper**och klicka sedan på **Borttagna grupper**.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="1e8ed-127">Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="1e8ed-128">I vissa fall kan det ta upp till 24 timmar innan gruppen och alla dess data återställs.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="1e8ed-129">Ta bort en Microsoft 365-grupp permanent</span><span class="sxs-lookup"><span data-stu-id="1e8ed-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="1e8ed-130">Ibland kanske du vill rensa en grupp permanent utan att vänta på att 30-dagarssperiod för mjuk borttagning ska löpa ut.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="1e8ed-131">Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="1e8ed-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="1e8ed-132">Ta del av objekt-ID för gruppen, eller grupperna, som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1e8ed-133">Borttagningen av gruppen raderar gruppen och allt innehåll för alltid.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="1e8ed-134">Om du vill ta bort gruppen kör du det här kommandot i PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8ed-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="1e8ed-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span></span> <span data-ttu-id="1e8ed-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="1e8ed-137">Har du frågor om Microsoft 365 Groups?</span><span class="sxs-lookup"><span data-stu-id="1e8ed-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="1e8ed-138">Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="1e8ed-139">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="1e8ed-139">Related articles</span></span>

[<span data-ttu-id="1e8ed-140">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8ed-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="1e8ed-141">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="1e8ed-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="1e8ed-142">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="1e8ed-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="1e8ed-143">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="1e8ed-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
