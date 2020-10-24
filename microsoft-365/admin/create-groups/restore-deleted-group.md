---
title: Återställa en borttagen Microsoft 365-grupp
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
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753249"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="97c85-103">Återställa en borttagen Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="97c85-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="97c85-104">Om du har tagit bort en grupp sparas den i 30 dagar som standard.</span><span class="sxs-lookup"><span data-stu-id="97c85-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="97c85-105">Denna 30-dagars period anses vara "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="97c85-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="97c85-106">Efter 30 dagar tas gruppen och dess tillhör ande innehåll bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="97c85-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="97c85-107">När du återställer en grupp återställs följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="97c85-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="97c85-108">Azure Active Directory (AD) Microsoft 365 grupperar objekt, egenskaper och medlemmar.</span><span class="sxs-lookup"><span data-stu-id="97c85-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="97c85-109">Gruppens e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="97c85-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="97c85-110">Delad inkorg och kalender för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="97c85-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="97c85-111">SharePoint Online-gruppwebbplats och-filer.</span><span class="sxs-lookup"><span data-stu-id="97c85-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="97c85-112">OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="97c85-112">OneNote notebook</span></span>
    
- <span data-ttu-id="97c85-113">Planner</span><span class="sxs-lookup"><span data-stu-id="97c85-113">Planner</span></span>
    
- <span data-ttu-id="97c85-114">Teams</span><span class="sxs-lookup"><span data-stu-id="97c85-114">Teams</span></span>

- <span data-ttu-id="97c85-115">Grupp-och grupp innehåll i Yammer (om Microsoft 365-gruppen skapades från Yammer)</span><span class="sxs-lookup"><span data-stu-id="97c85-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="97c85-116">I den här artikeln beskrivs hur du återställer bara Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="97c85-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="97c85-117">Alla andra grupper kan inte återställas när de har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="97c85-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="97c85-118">Återställa en grupp</span><span class="sxs-lookup"><span data-stu-id="97c85-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="97c85-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="97c85-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="97c85-120">Om du är ägare till en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="97c85-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="97c85-121">Välj alternativet **hantera grupper** under noden **grupper** på [sidan borttagna grupper](https://outlook.office.com/people/group/deleted)och välj sedan **Borttaget**.</span><span class="sxs-lookup"><span data-stu-id="97c85-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="97c85-122">Klicka på fliken **Återställ** bredvid den grupp du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="97c85-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="97c85-123">Om den borttagna gruppen inte visas här kan du kontakta en administratör.</span><span class="sxs-lookup"><span data-stu-id="97c85-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="97c85-124">Administrations Center</span><span class="sxs-lookup"><span data-stu-id="97c85-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="97c85-125">Om du är global administratör eller administratör för administratörer kan du återställa en borttagen grupp i administrations centret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="97c85-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="97c85-126">Gå till [administrations centret](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="97c85-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="97c85-127">Expandera **grupper**och klicka sedan på **borttagna grupper**.</span><span class="sxs-lookup"><span data-stu-id="97c85-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="97c85-128">Markera den grupp du vill återställa och klicka sedan på **Återställ grupp**.</span><span class="sxs-lookup"><span data-stu-id="97c85-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="97c85-129">I vissa fall kan det ta så lång tid som 24 timmar för gruppen och alla dess data att återställas.</span><span class="sxs-lookup"><span data-stu-id="97c85-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="97c85-130">Har du frågor om Microsoft 365-grupper?</span><span class="sxs-lookup"><span data-stu-id="97c85-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="97c85-131">Besök [Microsofts Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att publicera frågor och delta i konversationer om Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="97c85-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="97c85-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="97c85-132">Related articles</span></span>

[<span data-ttu-id="97c85-133">Hantera Microsoft 365-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="97c85-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="97c85-134">Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="97c85-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="97c85-135">Hantera dina grupprelaterade gruppwebbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="97c85-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="97c85-136">Ta bort en grupp i Outlook</span><span class="sxs-lookup"><span data-stu-id="97c85-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
