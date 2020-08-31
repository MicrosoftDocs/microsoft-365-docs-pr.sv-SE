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
ms.openlocfilehash: 8fb2cb3afdf390efae7854a040bb56df731cceaf
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307193"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="6a74f-103">Återställa en borttagen grupp</span><span class="sxs-lookup"><span data-stu-id="6a74f-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6a74f-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="6a74f-104">The admin center is changing.</span></span> <span data-ttu-id="6a74f-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6a74f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6a74f-106">Om du har tagit bort en grupp sparas den i 30 dagar som standard.</span><span class="sxs-lookup"><span data-stu-id="6a74f-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="6a74f-107">Denna 30-dagars period anses vara "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="6a74f-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="6a74f-108">Efter 30 dagar tas gruppen och dess tillhör ande innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="6a74f-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="6a74f-109">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="6a74f-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="6a74f-110">Azure Active Directory (AD) Microsoft 365 grupperar objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="6a74f-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="6a74f-111">Gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="6a74f-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="6a74f-112">Delad inkorg och kalender för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6a74f-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="6a74f-113">SharePoint Online-gruppwebbplats och-filer.</span><span class="sxs-lookup"><span data-stu-id="6a74f-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="6a74f-114">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="6a74f-114">OneNote notebook</span></span>
    
- <span data-ttu-id="6a74f-115">Planner</span><span class="sxs-lookup"><span data-stu-id="6a74f-115">Planner</span></span>
    
- <span data-ttu-id="6a74f-116">Teams</span><span class="sxs-lookup"><span data-stu-id="6a74f-116">Teams</span></span>

- <span data-ttu-id="6a74f-117">Grupp-och grupp innehåll i Yammer (om Microsoft 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="6a74f-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="6a74f-118">Återställa en grupp som du äger med hjälp av Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="6a74f-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="6a74f-119">Om du är ägare till en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="6a74f-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="6a74f-120">Välj alternativet **hantera grupper** under noden **grupper** på [sidan borttagna grupper](https://outlook.office.com/people/group/deleted)och välj sedan **Borttaget**.</span><span class="sxs-lookup"><span data-stu-id="6a74f-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="6a74f-121">Klicka på fliken **Återställ** bredvid den grupp du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="6a74f-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="6a74f-122">Om den borttagna gruppen inte visas här kan du kontakta en administratör.</span><span class="sxs-lookup"><span data-stu-id="6a74f-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6a74f-123">Återställa en grupp i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a74f-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6a74f-124">Om du är global administratör eller administratör för administratörer kan du återställa en borttagen grupp i administrations centret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6a74f-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="6a74f-125">Gå till [administrations centret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6a74f-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="6a74f-126">Expandera **grupper**och klicka sedan på **borttagna grupper**.</span><span class="sxs-lookup"><span data-stu-id="6a74f-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="6a74f-127">Markera den grupp du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="6a74f-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a74f-128">I vissa fall kan det ta så lång tid som 24 timmar för gruppen och alla dess data att återställas.</span><span class="sxs-lookup"><span data-stu-id="6a74f-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="6a74f-129">Ta bort en Microsoft 365-grupp permanent</span><span class="sxs-lookup"><span data-stu-id="6a74f-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="6a74f-130">Ibland kanske du vill ta bort en grupp permanent utan att vänta på att den 30 dagars borttagnings perioden upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="6a74f-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="6a74f-131">Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="6a74f-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="6a74f-132">Anteckna objekt-ID: t för gruppen som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="6a74f-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6a74f-133">Borttagningen av gruppen raderar gruppen och allt innehåll för alltid.</span><span class="sxs-lookup"><span data-stu-id="6a74f-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="6a74f-134">Om du vill ta bort gruppen kör du det här kommandot i PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a74f-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="6a74f-p104">För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="6a74f-p104">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="6a74f-137">Har du frågor om Microsoft 365-grupper?</span><span class="sxs-lookup"><span data-stu-id="6a74f-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="6a74f-138">Besök [Microsofts Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att publicera frågor och delta i konversationer om Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="6a74f-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="6a74f-139">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6a74f-139">Related articles</span></span>

[<span data-ttu-id="6a74f-140">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a74f-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="6a74f-141">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6a74f-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="6a74f-142">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="6a74f-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="6a74f-143">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="6a74f-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
