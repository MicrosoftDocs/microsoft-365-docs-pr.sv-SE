---
title: Lägga till lagringsutrymme för din prenumeration
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Lär dig att lägga till och minska fillagringen i Microsoft 365-prenumerationen. Med extra fillagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: 98fdb4412f263bd9e0a22b6890ff66509cb3e799
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332192"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="d392c-104">Lägga till lagringsutrymme för din prenumeration</span><span class="sxs-lookup"><span data-stu-id="d392c-104">Add storage space for your subscription</span></span>

<span data-ttu-id="d392c-105">Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det.</span><span class="sxs-lookup"><span data-stu-id="d392c-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="d392c-106">Om Du inte ser **Office 365 Extra** fillagring i listan med tillgängliga tillägg innebär det att ditt abonnemang inte är berättigande.</span><span class="sxs-lookup"><span data-stu-id="d392c-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="d392c-107">Mer information finns i [Är mitt abonnemang berättigande?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="d392c-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="d392c-108">Om du har köpt prenumerationen via volymlicensiering eller en molntjänsttjänst kan du inte köpa **Office 365 extra fillagring** för din organisation direkt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d392c-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="d392c-109">Kontakta din representant eller partner om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="d392c-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d392c-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d392c-110">Before you begin</span></span>

<span data-ttu-id="d392c-111">Du måste vara global administratör eller SharePoint-administratör för att kunna utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d392c-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="d392c-112">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d392c-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="d392c-113">Visa tillgängligt lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="d392c-113">View available storage</span></span>

1. <span data-ttu-id="d392c-114">I administrationscentret för SharePoint <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> går du till sidan Aktiva webbplatser och loggar in med ett konto som har [administratörsbehörigheter](/sharepoint/sharepoint-admin-role) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d392c-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="d392c-115">Längst upp till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d392c-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="d392c-116">Om organisationen har konfigurerat Multi-Geo i Office 365 visar stapeln också hur mycket lagringsutrymme som används för alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="d392c-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Lagringsfältet på sidan Aktiva webbplatser](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="d392c-118">Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="d392c-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="d392c-119">När du har tagit reda på hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d392c-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="d392c-120">Följ stegen i den här artikeln för att ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan du köper mer.</span><span class="sxs-lookup"><span data-stu-id="d392c-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="d392c-121">Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="d392c-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="d392c-122">Lägga till lagringsutrymme i din prenumeration</span><span class="sxs-lookup"><span data-stu-id="d392c-122">Add storage to your subscription</span></span>

<span data-ttu-id="d392c-123">Om du ännu inte har köpt extra lagringsutrymme för din prenumeration kan du göra det.</span><span class="sxs-lookup"><span data-stu-id="d392c-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="d392c-124">I administrationscentret går du  till sidan \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Faktureringsköpstjänster.</a></span><span class="sxs-lookup"><span data-stu-id="d392c-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="d392c-125">Längst ned på sidan **Köp** tjänster, i avsnittet Tillägg, hittar **du Office 365 extra fillagring** och väljer **Information**. </span><span class="sxs-lookup"><span data-stu-id="d392c-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="d392c-126">På sidan med produktinformation väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d392c-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="d392c-127">Om det behövs väljer du basprenumerationen och anger sedan antalet gigabyte lagringsutrymme som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="d392c-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="d392c-128">Välj **Gå till utcheckningen nu.**</span><span class="sxs-lookup"><span data-stu-id="d392c-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="d392c-129">På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, granskar prisinformationen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d392c-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="d392c-130">Verifiera **summan på** sidan Slutför beställningen.</span><span class="sxs-lookup"><span data-stu-id="d392c-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="d392c-131">Om du behöver göra några ändringar väljer du **Redigera ordning**.</span><span class="sxs-lookup"><span data-stu-id="d392c-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="d392c-132">Om ordern kräver en kreditkontroll markerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="d392c-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="d392c-133">När du är klar väljer du **Lägg order Gå** till startsidan för \> **administratör.**</span><span class="sxs-lookup"><span data-stu-id="d392c-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="d392c-134">Öka eller minska lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="d392c-134">Increase or decrease storage</span></span>

<span data-ttu-id="d392c-135">Om du redan har köpt extra fillagring via tillägget **Office 365 extra** fillagring kan du följa de här stegen om du vill öka eller minska det extra lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d392c-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="d392c-136">Du kan minska lagringen till så lite som 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="d392c-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="d392c-137">Kontakta support om du vill ta bort allt [extra lagringsutrymme.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="d392c-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="d392c-138">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="d392c-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d392c-139">På **fliken** Produkter väljer du den prenumeration som innehåller **tillägget Office 365 extra fillagring.**</span><span class="sxs-lookup"><span data-stu-id="d392c-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="d392c-140">Välj Hantera tillägg i **avsnittet Tillägg på sidan** med **produktinformation.**</span><span class="sxs-lookup"><span data-stu-id="d392c-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="d392c-141">Välj **Office** **365** Extra **Fillagring** i listan Tillägg i fönstret Hantera tillägg.</span><span class="sxs-lookup"><span data-stu-id="d392c-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="d392c-142">I **textrutan** Antal anger du antalet GBS lagringsutrymme som du vill använda för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="d392c-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="d392c-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d392c-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="d392c-144">Berättigar mitt abonnemang till Office 365 extra fillagring?</span><span class="sxs-lookup"><span data-stu-id="d392c-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="d392c-145">Office 365 extra fillagring är tillgängligt för följande prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="d392c-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="d392c-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d392c-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="d392c-147">Office 365 Enterprise, E2</span><span class="sxs-lookup"><span data-stu-id="d392c-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="d392c-148">Office 365 Enterprise, E3</span><span class="sxs-lookup"><span data-stu-id="d392c-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="d392c-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="d392c-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="d392c-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="d392c-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="d392c-151">Office för webben med SharePoint abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="d392c-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="d392c-152">Office för webben med SharePoint abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="d392c-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="d392c-153">SharePoint Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="d392c-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="d392c-154">SharePoint Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="d392c-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="d392c-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="d392c-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="d392c-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="d392c-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="d392c-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d392c-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="d392c-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="d392c-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="d392c-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d392c-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="d392c-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="d392c-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="d392c-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span><span class="sxs-lookup"><span data-stu-id="d392c-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="d392c-162">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="d392c-162">Related content</span></span>

<span data-ttu-id="d392c-163">[Hantera lagringsgränser för webbplatser](/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d392c-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="d392c-164">[Ange standardlagringsutrymme för OneDrive-användare](/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="d392c-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
