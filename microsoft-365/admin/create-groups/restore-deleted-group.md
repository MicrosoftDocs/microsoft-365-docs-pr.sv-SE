---
title: Återställa en borttagen Office 365-grupp
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
description: Lär dig hur du återställer en borttagen Office 365-grupp.
ms.openlocfilehash: 2efd8c35286d224c6a3ed185043c82ab4b8e954e
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547538"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="93fe1-103">Återställa en borttagen Office 365-grupp</span><span class="sxs-lookup"><span data-stu-id="93fe1-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="93fe1-104">Om du har tagit bort en grupp behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="93fe1-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="93fe1-105">Denna 30-dagarsperiod anses vara en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="93fe1-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="93fe1-106">Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="93fe1-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="93fe1-107">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="93fe1-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="93fe1-108">Azure Active Directory (AD) Office 365-grupper objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="93fe1-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="93fe1-109">gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="93fe1-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="93fe1-110">Exchange Online delad inkorg och kalender.</span><span class="sxs-lookup"><span data-stu-id="93fe1-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="93fe1-111">SharePoint Online-gruppwebbplats och -filer.</span><span class="sxs-lookup"><span data-stu-id="93fe1-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="93fe1-112">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="93fe1-112">OneNote notebook</span></span>
    
- <span data-ttu-id="93fe1-113">Planner</span><span class="sxs-lookup"><span data-stu-id="93fe1-113">Planner</span></span>
    
- <span data-ttu-id="93fe1-114">Teams</span><span class="sxs-lookup"><span data-stu-id="93fe1-114">Teams</span></span>

- <span data-ttu-id="93fe1-115">Yammer-grupp- och gruppinnehåll (Om Office 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="93fe1-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="93fe1-116">Återställa en grupp som du äger med Outlook</span><span class="sxs-lookup"><span data-stu-id="93fe1-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="93fe1-117">Om du äger en Office 365-grupp kan du återställa gruppen själv i Outlook genom att följa följande:</span><span class="sxs-lookup"><span data-stu-id="93fe1-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="93fe1-118">På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.</span><span class="sxs-lookup"><span data-stu-id="93fe1-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="93fe1-119">Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="93fe1-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="93fe1-120">Om den borttagna gruppen inte visas här kontaktar du en administratör.</span><span class="sxs-lookup"><span data-stu-id="93fe1-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="93fe1-121">Återställa en grupp i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93fe1-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="93fe1-122">Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i microsoft 365-administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="93fe1-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="93fe1-123">Gå till [administrationscentret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="93fe1-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="93fe1-124">Expandera **grupper**och klicka sedan på **Borttagna grupper**.</span><span class="sxs-lookup"><span data-stu-id="93fe1-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="93fe1-125">Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="93fe1-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="93fe1-126">Ta bort en Office 365-grupp permanent</span><span class="sxs-lookup"><span data-stu-id="93fe1-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="93fe1-127">Ibland kanske du vill rensa en grupp permanent utan att vänta på att 30-dagars perioden för mjuk borttagning ska löpa ut.</span><span class="sxs-lookup"><span data-stu-id="93fe1-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="93fe1-128">Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="93fe1-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="93fe1-129">Ta del av objekt-ID för gruppen, eller grupperna, som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="93fe1-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="93fe1-130">Borttagningen av gruppen raderar gruppen och allt innehåll för alltid.</span><span class="sxs-lookup"><span data-stu-id="93fe1-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="93fe1-131">Om du vill ta bort gruppen kör du det här kommandot i PowerShell</span><span class="sxs-lookup"><span data-stu-id="93fe1-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="93fe1-p103">För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="93fe1-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="93fe1-134">Har du frågor om Office 365-grupper?</span><span class="sxs-lookup"><span data-stu-id="93fe1-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="93fe1-135">Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="93fe1-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="93fe1-136">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="93fe1-136">Related articles</span></span>

[<span data-ttu-id="93fe1-137">Manage Office 365 Groups with PowerShell</span><span class="sxs-lookup"><span data-stu-id="93fe1-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="93fe1-138">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="93fe1-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="93fe1-139">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="93fe1-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="93fe1-140">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="93fe1-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
