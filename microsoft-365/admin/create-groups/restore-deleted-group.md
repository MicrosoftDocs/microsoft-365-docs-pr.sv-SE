---
title: Återställa en borttagna Microsoft 365 grupp
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
description: En borttagna grupp behålls i 30 dagar och du kan fortfarande återställa gruppen. Efter 30 dagar tas gruppen och dess innehåll bort permanent.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635744"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="2477c-104">Återställa en borttagna Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="2477c-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="2477c-105">Om du har tagit bort en grupp behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2477c-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="2477c-106">Den här 30-dagarsperioden betraktas som en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="2477c-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="2477c-107">Efter 30 dagar tas gruppen och dess tillhörande innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="2477c-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="2477c-108">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="2477c-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="2477c-109">Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="2477c-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="2477c-110">Gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="2477c-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="2477c-111">Exchange Online delad inkorg och kalender.</span><span class="sxs-lookup"><span data-stu-id="2477c-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="2477c-112">SharePoint Gruppwebbplats och filer online.</span><span class="sxs-lookup"><span data-stu-id="2477c-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="2477c-113">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="2477c-113">OneNote notebook</span></span>
    
- <span data-ttu-id="2477c-114">Planner</span><span class="sxs-lookup"><span data-stu-id="2477c-114">Planner</span></span>
    
- <span data-ttu-id="2477c-115">Teams</span><span class="sxs-lookup"><span data-stu-id="2477c-115">Teams</span></span>

- <span data-ttu-id="2477c-116">Yammer gruppera och gruppera innehåll (om Microsoft 365 gruppen har skapats Yammer)</span><span class="sxs-lookup"><span data-stu-id="2477c-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="2477c-117">I den här artikeln beskrivs endast återställning Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="2477c-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="2477c-118">Alla andra grupper kan inte återställas när de tagits bort.</span><span class="sxs-lookup"><span data-stu-id="2477c-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="2477c-119">Återställa en grupp</span><span class="sxs-lookup"><span data-stu-id="2477c-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="2477c-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="2477c-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="2477c-121">Om du är ägare till en Microsoft 365 grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="2477c-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="2477c-122">På sidan [Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du **alternativet Hantera grupper** under noden **Grupper** och väljer sedan **Borttagna**.</span><span class="sxs-lookup"><span data-stu-id="2477c-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="2477c-123">Klicka på **fliken** Återställ bredvid den grupp som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="2477c-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="2477c-124">Om den borttagna gruppen inte visas här kontaktar du administratören.</span><span class="sxs-lookup"><span data-stu-id="2477c-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="2477c-125">Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="2477c-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="2477c-126">Om du är global administratör eller gruppadministratör kan du återställa en borttagna grupp Microsoft 365 administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="2477c-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="2477c-127">Gå till [administrationscentret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2477c-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="2477c-128">Expandera **Grupper** och klicka sedan på **Borttagna grupper.**</span><span class="sxs-lookup"><span data-stu-id="2477c-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="2477c-129">Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="2477c-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="2477c-130">I vissa fall kan det ta upp till ett dygn för gruppen och alla data att återställas.</span><span class="sxs-lookup"><span data-stu-id="2477c-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="2477c-131">Har du frågor Microsoft 365 grupper?</span><span class="sxs-lookup"><span data-stu-id="2477c-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="2477c-132">Besök [Microsoft Tech Community om du](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vill ställa frågor och delta i konversationer om Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="2477c-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="2477c-133">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="2477c-133">Related content</span></span>

<span data-ttu-id="2477c-134">[Hantera Microsoft 365-grupper med PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2477c-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="2477c-135">[Ta bort grupper med Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2477c-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="2477c-136">[Hantera dina gruppanslutna gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2477c-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="2477c-137">[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2477c-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>