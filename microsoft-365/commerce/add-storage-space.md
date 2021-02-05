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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du lägger till och minskar fillagringen i Microsoft 365-prenumerationen. Med extra fillagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114913"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="aefa2-104">Lägga till lagringsutrymme för din prenumeration</span><span class="sxs-lookup"><span data-stu-id="aefa2-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="aefa2-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="aefa2-105">The admin center is changing.</span></span> <span data-ttu-id="aefa2-106">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="aefa2-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="aefa2-107">Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det.</span><span class="sxs-lookup"><span data-stu-id="aefa2-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="aefa2-108">Om du inte ser **Office 365 Extra** fillagring i listan med tillgängliga tillägg innebär det att ditt abonnemang inte är berättigande.</span><span class="sxs-lookup"><span data-stu-id="aefa2-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="aefa2-109">Mer information finns i [Är mitt abonnemang berättigande?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="aefa2-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="aefa2-110">Om du har köpt prenumerationen via volymlicensiering eller en molntjänst kan du inte köpa **Office 365 extra** fillagring för din organisation direkt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aefa2-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="aefa2-111">Kontakta din representant eller partner för att få hjälp.</span><span class="sxs-lookup"><span data-stu-id="aefa2-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="aefa2-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="aefa2-112">Before you begin</span></span>

<span data-ttu-id="aefa2-113">Du måste vara global administratör eller SharePoint-administratör för att kunna utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="aefa2-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="aefa2-114">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="aefa2-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="aefa2-115">Visa tillgängligt lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="aefa2-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="aefa2-116">Gå till sidan Aktiva webbplatser <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> i administrationscentret för SharePoint och logga in med ett konto som har [administratörsbehörighet](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="aefa2-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="aefa2-117">Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="aefa2-118">Om organisationen har konfigurerat Multi-Geo i Office 365 visar fältet också hur mycket lagringsutrymme som används för alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="aefa2-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="aefa2-120">Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="aefa2-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="aefa2-121">Logga in som https://portal.office.de global administratör eller SharePoint-administratör och välj sedan administratörspanelen för att öppna administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="aefa2-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="aefa2-122">Om ett meddelande visas om att du inte har behörighet att komma åt sidan betyder det att du inte har Administratörsbehörigheter för Microsoft 365 i din organisation.</span><span class="sxs-lookup"><span data-stu-id="aefa2-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="aefa2-123">Välj SharePoint i den **vänstra rutan under** **Administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="aefa2-124">Om det klassiska administrationscentret för  SharePoint visas väljer du Öppna nu högst upp på sidan för att öppna det nya administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aefa2-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="aefa2-125">Välj Aktiva webbplatser i den vänstra rutan i det nya administrationscentret **för** SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aefa2-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="aefa2-126">Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="aefa2-128">Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="aefa2-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="aefa2-129">Logga in som https://login.partner.microsoftonline.cn/ global administratör eller SharePoint-administratör och välj sedan administratörspanelen för att öppna administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="aefa2-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="aefa2-130">(Om ett meddelande visas om att du inte har behörighet att komma åt sidan betyder det att du inte har Administratörsbehörigheter för Microsoft 365 i din organisation.</span><span class="sxs-lookup"><span data-stu-id="aefa2-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="aefa2-131">Välj SharePoint i den **vänstra rutan under** **Administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="aefa2-132">Om det klassiska administrationscentret för  SharePoint visas väljer du Öppna nu högst upp på sidan för att öppna det nya administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aefa2-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="aefa2-133">Välj Aktiva webbplatser i den vänstra rutan i det nya administrationscentret **för** SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aefa2-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="aefa2-134">Uppe till höger på sidan ser du hur mycket lagringsutrymme som används på alla webbplatser och det totala lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Lagringsfält på sidan Aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="aefa2-136">Använt lagringsutrymme inkluderar inte ändringar som gjorts under de senaste 24–48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="aefa2-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="aefa2-p111">När du har fastställt hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration. Följ stegen i den här artikeln om du vill ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan köpet.</span><span class="sxs-lookup"><span data-stu-id="aefa2-p111">After you've determined how much storage you're using, you can add or remove storage space for your subscription. To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="aefa2-139">Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="aefa2-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="aefa2-140">Lägga till lagring i din prenumeration</span><span class="sxs-lookup"><span data-stu-id="aefa2-140">Add storage to your subscription</span></span>

<span data-ttu-id="aefa2-141">Om du ännu inte har köpt extra lagringsutrymme för prenumerationen kan du göra det.</span><span class="sxs-lookup"><span data-stu-id="aefa2-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="aefa2-142">Gå till sidan Faktureringsköpstjänster  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="aefa2-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="aefa2-143">Välj Tillägg **längst ned** på sidan **Köptjänster.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="aefa2-144">Välj **Office 365 extra fillagring.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="aefa2-145">På sidan Extra fillagring i **Office 365** väljer du basprenumerationen och anger sedan hur många GB lagringsutrymme du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="aefa2-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="aefa2-146">Välj **Gå till checka ut nu.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="aefa2-147">På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="aefa2-148">Verifiera **summan på** sidan Slutför order.</span><span class="sxs-lookup"><span data-stu-id="aefa2-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="aefa2-149">Om du behöver göra några ändringar väljer du **Redigera ordning.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="aefa2-150">Om ordern kräver en kreditkontroll markerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="aefa2-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="aefa2-151">När du är klar väljer du Lägg **order gå** \> **till administrationscentrets start.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="aefa2-152">Gå till sidan Faktureringsprenumerationer  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">i administrationscentret.</a>  </span><span class="sxs-lookup"><span data-stu-id="aefa2-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="aefa2-153">På **sidan** Prenumerationer väljer du den prenumeration där du vill lägga till lagringsutrymme och väljer **sedan Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="aefa2-155">Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="aefa2-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="aefa2-156">Välj **Köp tillägg.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-156">Select **Buy add-ons**.</span></span>

    ![Länken Köp tillägg på sidan Prenumerationer i administrationscentret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="aefa2-158">På sidan **Köptjänster** för du muspekaren över eller **trycker på Office 365 Extra** fillagring och väljer sedan Köp **nu.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="aefa2-159">Ange antalet användarlicenser du behöver och, om det visas, välj en basprenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="aefa2-160">Välj **Gå till checka ut nu.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="aefa2-161">På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="aefa2-162">Välj **Lägg order på** sidan **Slutför order.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="aefa2-163">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="aefa2-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="aefa2-164">På **sidan** Prenumerationer väljer du den prenumeration där du vill lägga till lagringsutrymme och väljer **sedan Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="aefa2-166">Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="aefa2-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="aefa2-167">Välj **Köp tillägg.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-167">Select **Buy add-ons**.</span></span>

    ![Länken Köp tillägg på sidan Prenumerationer i administrationscentret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="aefa2-169">På sidan **Köptjänster** för du muspekaren över eller **trycker på Office 365 Extra** fillagring och väljer sedan Köp **nu.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="aefa2-170">Ange antalet användarlicenser du behöver och, om det visas, välj en basprenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="aefa2-171">Välj **Gå till checka ut nu.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="aefa2-172">På sidan **Hur ser det ut?** kontrollerar du antalet gigabyte lagringsutrymme du har valt, kontrollerar prisinformationen och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="aefa2-173">Välj **Lägg order på** sidan **Slutför order.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="aefa2-174">Öka eller minska lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="aefa2-174">Increase or decrease storage</span></span>

<span data-ttu-id="aefa2-175">Om du redan har köpt extra lagringsutrymme via tillägget **Office 365 extra** fillagring kan du använda de här stegen till att öka eller minska det extra lagringsutrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="aefa2-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="aefa2-176">Du kan minska lagringsutrymmet till så lite som 1 GIGABYTE.</span><span class="sxs-lookup"><span data-stu-id="aefa2-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="aefa2-177">Kontakta support om du vill ta bort allt [extra lagringsutrymme.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="aefa2-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="aefa2-178">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="aefa2-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="aefa2-179">På fliken **Produkter** väljer du den prenumeration som innehåller **tillägget Office 365 extra fillagring.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="aefa2-180">Välj Hantera tillägg i **avsnittet Tillägg på sidan** **Produktinformation.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="aefa2-181">I fönstret **Hantera tillägg väljer** du  **Office 365 Extra fillagring i listan Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="aefa2-182">I **textrutan** Antal anger du antalet GBS lagringsutrymme som du vill använda för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="aefa2-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="aefa2-183">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="aefa2-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="aefa2-184">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="aefa2-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="aefa2-185">Välj  Tillägg på **sidan Prenumerationer.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="aefa2-187">Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="aefa2-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="aefa2-188">Välj **Ändra antal under Office 365 Extra** **fillagring.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="aefa2-190">I det högra fönstret anger du det totala antalet GIGABYTE du behöver och väljer sedan **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="aefa2-191">Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.</span><span class="sxs-lookup"><span data-stu-id="aefa2-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="aefa2-192">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="aefa2-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="aefa2-193">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="aefa2-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="aefa2-194">Välj **Tillägg** på **sidan Prenumerationer.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="aefa2-196">Om inga tillägg visas och prenumerationen har **köpts** via en partner väljer du **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="aefa2-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="aefa2-197">Välj **Ändra antal under Office 365 Extra** **fillagring.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="aefa2-199">I det högra fönstret anger du det totala antalet GIGABYTE du behöver och väljer sedan **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="aefa2-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="aefa2-200">Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.</span><span class="sxs-lookup"><span data-stu-id="aefa2-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="aefa2-201">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="aefa2-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="aefa2-202">Berättigar mitt abonnemang till Office 365 extra fillagring?</span><span class="sxs-lookup"><span data-stu-id="aefa2-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="aefa2-203">Office 365 extra fillagring är tillgängligt för följande prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="aefa2-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="aefa2-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="aefa2-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="aefa2-205">Office 365 Enterprise, E2</span><span class="sxs-lookup"><span data-stu-id="aefa2-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="aefa2-206">Office 365 Enterprise, E3</span><span class="sxs-lookup"><span data-stu-id="aefa2-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="aefa2-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="aefa2-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="aefa2-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="aefa2-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="aefa2-209">Office för webben med SharePoint abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="aefa2-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="aefa2-210">Office för webben med SharePoint abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="aefa2-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="aefa2-211">SharePoint Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="aefa2-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="aefa2-212">SharePoint Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="aefa2-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="aefa2-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="aefa2-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="aefa2-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="aefa2-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="aefa2-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="aefa2-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="aefa2-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="aefa2-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="aefa2-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="aefa2-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="aefa2-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="aefa2-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="aefa2-219">Office 365 Extra fillagring är också tillgängligt för GCC-, GCC High- och DOD-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="aefa2-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="aefa2-220">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="aefa2-220">Related content</span></span>

<span data-ttu-id="aefa2-221">[Hantera lagringsgränser för webbplatser](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="aefa2-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="aefa2-222">[Ange standardlagringsutrymme för OneDrive-användare](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="aefa2-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
