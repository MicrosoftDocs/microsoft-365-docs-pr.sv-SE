---
title: Lägga till lagringsutrymme för din prenumeration
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Lär dig hur du lägger till och minskar fillagringen i Microsoft 365-prenumerationen. Med extra fillagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405894"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="62753-104">Lägga till lagringsutrymme för din prenumeration</span><span class="sxs-lookup"><span data-stu-id="62753-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="62753-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="62753-105">The admin center is changing.</span></span> <span data-ttu-id="62753-106">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="62753-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="62753-107">Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det.</span><span class="sxs-lookup"><span data-stu-id="62753-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="62753-108">Om du inte ser **Office 365 Extra** fillagring i listan med tillgängliga tillägg innebär det att ditt abonnemang inte är berättigande.</span><span class="sxs-lookup"><span data-stu-id="62753-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="62753-109">Mer information finns i [Är mitt abonnemang berättigande?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="62753-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="62753-110">Om du har köpt prenumerationen via volymlicensiering eller en microsoft-molntjänst kan du inte köpa **Office 365 extra** fillagring för din organisation direkt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62753-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="62753-111">Kontakta din representant eller partner för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="62753-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="62753-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="62753-112">Before you begin</span></span>

<span data-ttu-id="62753-113">Du måste vara global administratör eller SharePoint-administratör för att kunna utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="62753-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="62753-114">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="62753-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="62753-115">Visa tillgängligt lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="62753-115">View available storage</span></span>

1. <span data-ttu-id="62753-116">Gå till sidan Aktiva webbplatser <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> i administrationscentret för SharePoint och logga in med ett konto som har [administratörsbehörighet](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="62753-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="62753-117">Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="62753-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="62753-118">Om organisationen har konfigurerat Multi-Geo i Office 365 visar fältet också hur mycket lagringsutrymme som används för alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="62753-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="62753-120">Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="62753-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="62753-121">När du har tagit reda på hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="62753-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="62753-122">Följ stegen i den här artikeln för att ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan du köper mer.</span><span class="sxs-lookup"><span data-stu-id="62753-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="62753-123">Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="62753-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="62753-124">Lägga till lagring i din prenumeration</span><span class="sxs-lookup"><span data-stu-id="62753-124">Add storage to your subscription</span></span>

<span data-ttu-id="62753-125">Om du ännu inte har köpt extra lagringsutrymme för prenumerationen kan du göra det.</span><span class="sxs-lookup"><span data-stu-id="62753-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="62753-126">Gå till sidan Faktureringsköpstjänster  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="62753-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="62753-127">Längst ned på sidan **Köptjänster,** i avsnittet Tillägg, hittar **du Office 365 Extra** fillagring och väljer **Information.** </span><span class="sxs-lookup"><span data-stu-id="62753-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="62753-128">Välj Nästa på sidan med **produktinformation.**</span><span class="sxs-lookup"><span data-stu-id="62753-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="62753-129">Om det behövs väljer du basprenumerationen och anger sedan antalet gigabyte lagringsutrymme som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="62753-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="62753-130">Välj **Gå till checka ut nu.**</span><span class="sxs-lookup"><span data-stu-id="62753-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="62753-131">På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="62753-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="62753-132">Verifiera **summan på** sidan Slutför order.</span><span class="sxs-lookup"><span data-stu-id="62753-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="62753-133">Om du behöver göra några ändringar väljer du **Redigera ordning.**</span><span class="sxs-lookup"><span data-stu-id="62753-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="62753-134">Om ordern kräver en kreditkontroll markerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="62753-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="62753-135">När du är klar väljer du Lägg **order gå** \> **till administrationscentrets start.**</span><span class="sxs-lookup"><span data-stu-id="62753-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="62753-136">Öka eller minska lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="62753-136">Increase or decrease storage</span></span>

<span data-ttu-id="62753-137">Om du redan har köpt extra lagringsutrymme via tillägget **Office 365 extra** fillagring kan du använda de här stegen till att öka eller minska det extra lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="62753-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="62753-138">Du kan minska lagringsutrymmet till så lite som 1 GIGABYTE.</span><span class="sxs-lookup"><span data-stu-id="62753-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="62753-139">Kontakta support om du vill ta bort allt [extra lagringsutrymme.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="62753-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="62753-140">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="62753-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="62753-141">På fliken **Produkter** väljer du den prenumeration som innehåller **tillägget Office 365 extra fillagring.**</span><span class="sxs-lookup"><span data-stu-id="62753-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="62753-142">Välj Hantera tillägg i **avsnittet Tillägg på sidan** **Produktinformation.**</span><span class="sxs-lookup"><span data-stu-id="62753-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="62753-143">I fönstret **Hantera tillägg väljer** du  **Office 365 Extra fillagring i listan Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="62753-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="62753-144">I **textrutan** Antal anger du antalet GBS lagringsutrymme som du vill använda för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="62753-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="62753-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="62753-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="62753-146">Berättigar mitt abonnemang till Office 365 extra fillagring?</span><span class="sxs-lookup"><span data-stu-id="62753-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="62753-147">Office 365 extra fillagring är tillgängligt för följande prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="62753-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="62753-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="62753-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="62753-149">Office 365 Enterprise, E2</span><span class="sxs-lookup"><span data-stu-id="62753-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="62753-150">Office 365 Enterprise, E3</span><span class="sxs-lookup"><span data-stu-id="62753-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="62753-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="62753-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="62753-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="62753-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="62753-153">Office för webben med SharePoint abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="62753-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="62753-154">Office för webben med SharePoint abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="62753-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="62753-155">SharePoint Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="62753-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="62753-156">SharePoint Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="62753-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="62753-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="62753-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="62753-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="62753-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="62753-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="62753-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="62753-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="62753-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="62753-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="62753-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="62753-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="62753-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="62753-163">Office 365 Extra fillagring är också tillgängligt för GCC-, GCC High- och DOD-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="62753-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="62753-164">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="62753-164">Related content</span></span>

<span data-ttu-id="62753-165">[Hantera lagringsgränser för webbplatser](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62753-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="62753-166">[Ange standardlagringsutrymme för OneDrive-användare](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="62753-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>