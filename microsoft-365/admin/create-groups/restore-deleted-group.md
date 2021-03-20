---
title: Återställa en borttagna Microsoft 365-grupp
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Lär dig återställa en borttagna Microsoft 365-grupp.
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910552"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="c982b-103">Återställa en borttagna Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="c982b-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="c982b-104">Om du har tagit bort en grupp behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="c982b-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="c982b-105">Den här 30-dagarsperioden betraktas som en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="c982b-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="c982b-106">Efter 30 dagar tas gruppen och dess tillhörande innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="c982b-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="c982b-107">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="c982b-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="c982b-108">Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c982b-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="c982b-109">Gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="c982b-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="c982b-110">Delad inkorg och kalender i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c982b-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="c982b-111">SharePoint Online-gruppwebbplats och filer.</span><span class="sxs-lookup"><span data-stu-id="c982b-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="c982b-112">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="c982b-112">OneNote notebook</span></span>
    
- <span data-ttu-id="c982b-113">Planner</span><span class="sxs-lookup"><span data-stu-id="c982b-113">Planner</span></span>
    
- <span data-ttu-id="c982b-114">Teams</span><span class="sxs-lookup"><span data-stu-id="c982b-114">Teams</span></span>

- <span data-ttu-id="c982b-115">Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="c982b-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="c982b-116">I den här artikeln beskrivs återställning av endast Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c982b-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="c982b-117">Alla andra grupper kan inte återställas när de tagits bort.</span><span class="sxs-lookup"><span data-stu-id="c982b-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="c982b-118">Återställa en grupp</span><span class="sxs-lookup"><span data-stu-id="c982b-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="c982b-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="c982b-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="c982b-120">Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="c982b-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="c982b-121">På sidan [Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du **alternativet Hantera grupper** under noden **Grupper** och väljer sedan **Borttagna**.</span><span class="sxs-lookup"><span data-stu-id="c982b-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="c982b-122">Klicka på **fliken** Återställ bredvid den grupp som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="c982b-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="c982b-123">Om den borttagna gruppen inte visas här kontaktar du administratören.</span><span class="sxs-lookup"><span data-stu-id="c982b-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="c982b-124">Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="c982b-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="c982b-125">Om du är global administratör eller gruppadministratör kan du återställa en borttagna grupp i administrationscentret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c982b-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="c982b-126">Gå till [administrationscentret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c982b-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c982b-127">Expandera **Grupper** och klicka sedan på **Borttagna grupper.**</span><span class="sxs-lookup"><span data-stu-id="c982b-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="c982b-128">Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="c982b-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="c982b-129">I vissa fall kan det ta upp till ett dygn för gruppen och alla data att återställas.</span><span class="sxs-lookup"><span data-stu-id="c982b-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="c982b-130">Har du frågor om Microsoft 365-grupper?</span><span class="sxs-lookup"><span data-stu-id="c982b-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="c982b-131">Besök [Microsoft Tech Community om du](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vill ställa frågor och delta i konversationer om Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c982b-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="c982b-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="c982b-132">Related articles</span></span>

[<span data-ttu-id="c982b-133">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="c982b-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="c982b-134">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c982b-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="c982b-135">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="c982b-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="c982b-136">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="c982b-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)