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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: 870db3c92cd1f28f91540633a1dce9d0353c2b87
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049161"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="7fee6-103">Återställa en borttagen grupp</span><span class="sxs-lookup"><span data-stu-id="7fee6-103">Restore a deleted Group</span></span>

<span data-ttu-id="7fee6-104">Om du har tagit bort en grupp behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="7fee6-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="7fee6-105">Denna 30-dagarsperiod anses vara en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="7fee6-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="7fee6-106">Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="7fee6-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="7fee6-107">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="7fee6-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="7fee6-108">Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="7fee6-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="7fee6-109">gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="7fee6-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="7fee6-110">Exchange Online delad inkorg och kalender.</span><span class="sxs-lookup"><span data-stu-id="7fee6-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="7fee6-111">SharePoint Online-gruppwebbplats och -filer.</span><span class="sxs-lookup"><span data-stu-id="7fee6-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="7fee6-112">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="7fee6-112">OneNote notebook</span></span>
    
- <span data-ttu-id="7fee6-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7fee6-113">Planner</span></span>
    
- <span data-ttu-id="7fee6-114">Teams</span><span class="sxs-lookup"><span data-stu-id="7fee6-114">Teams</span></span>

- <span data-ttu-id="7fee6-115">Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="7fee6-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="7fee6-116">Återställa en grupp som du äger med Outlook</span><span class="sxs-lookup"><span data-stu-id="7fee6-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="7fee6-117">Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook genom att följa följande:</span><span class="sxs-lookup"><span data-stu-id="7fee6-117">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="7fee6-118">På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.</span><span class="sxs-lookup"><span data-stu-id="7fee6-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="7fee6-119">Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="7fee6-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="7fee6-120">Om den borttagna gruppen inte visas här kontaktar du en administratör.</span><span class="sxs-lookup"><span data-stu-id="7fee6-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7fee6-121">Återställa en grupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7fee6-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="7fee6-122">Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i microsoft 365-administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="7fee6-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="7fee6-123">Gå till [administrationscentret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7fee6-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="7fee6-124">Expandera **grupper**och klicka sedan på **Borttagna grupper**.</span><span class="sxs-lookup"><span data-stu-id="7fee6-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="7fee6-125">Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="7fee6-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="7fee6-126">Ta bort en Microsoft 365-grupp permanent</span><span class="sxs-lookup"><span data-stu-id="7fee6-126">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="7fee6-127">Ibland kanske du vill rensa en grupp permanent utan att vänta på att 30-dagars perioden för mjuk borttagning ska löpa ut.</span><span class="sxs-lookup"><span data-stu-id="7fee6-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="7fee6-128">Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="7fee6-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="7fee6-129">Ta del av objekt-ID för gruppen, eller grupperna, som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="7fee6-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7fee6-130">Borttagningen av gruppen raderar gruppen och allt innehåll för alltid.</span><span class="sxs-lookup"><span data-stu-id="7fee6-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="7fee6-131">Om du vill ta bort gruppen kör du det här kommandot i PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fee6-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="7fee6-p103">För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="7fee6-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="7fee6-134">Har du frågor om Microsoft 365 Groups?</span><span class="sxs-lookup"><span data-stu-id="7fee6-134">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="7fee6-135">Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="7fee6-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="7fee6-136">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7fee6-136">Related articles</span></span>

[<span data-ttu-id="7fee6-137">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fee6-137">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="7fee6-138">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="7fee6-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="7fee6-139">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="7fee6-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="7fee6-140">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="7fee6-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
