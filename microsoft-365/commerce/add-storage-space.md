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
description: Lär dig hur du lägger till och minskar fil lagringen i Microsoft 365-prenumerationen. Med extra fil lagring kan du lagra mer innehåll i SharePoint Online och OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324474"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="17b12-104">Lägga till lagringsutrymme för din prenumeration</span><span class="sxs-lookup"><span data-stu-id="17b12-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="17b12-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="17b12-105">The admin center is changing.</span></span> <span data-ttu-id="17b12-106">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="17b12-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="17b12-107">Om du börjar få slut på lagringsutrymme för webbplatssamlingar i SharePoint Online kan du lägga till lagringsutrymme för din prenumeration om prenumerationen är berättigad till det.</span><span class="sxs-lookup"><span data-stu-id="17b12-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="17b12-108">Om du inte ser **Office 365 extra File Storage** i listan med tillgängliga tillägg innebär det att din plan inte är berättigad.</span><span class="sxs-lookup"><span data-stu-id="17b12-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="17b12-109">Mer information finns i finns [Min plan-kvalificerare?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="17b12-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="17b12-110">Om du har köpt ditt abonnemang via volym licensiering eller en KRYPTOGRAFIPROVIDER kan du inte köpa **Office 365 extra fil lagring** för organisationen direkt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17b12-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="17b12-111">Kontakta din representant eller partner för hjälp.</span><span class="sxs-lookup"><span data-stu-id="17b12-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="17b12-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="17b12-112">Before you begin</span></span>

<span data-ttu-id="17b12-113">Du måste vara global eller SharePoint-administratör för att utföra åtgärderna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="17b12-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="17b12-114">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="17b12-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="17b12-115">Visa tillgängligt lagrings utrymme</span><span class="sxs-lookup"><span data-stu-id="17b12-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17b12-116">Gå till sidan <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">aktiva webbplatser</a> i administrations centret för SharePoint och logga in med ett konto som har [Administratörs behörigheter](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="17b12-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="17b12-117">I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="17b12-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="17b12-118">Om organisationen har konfigurerat multi-geo i Office 365, visar fältet även mängden lagrings utrymme som används för alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="17b12-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="17b12-120">Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="17b12-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17b12-121">Logga in på https://portal.office.de som global eller SharePoint-administratör och välj sedan administratörs panelen för att öppna administrations centret.</span><span class="sxs-lookup"><span data-stu-id="17b12-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="17b12-122">Om du ser ett meddelande om att du inte har behörighet att komma åt sidan innebär det att du inte har Microsoft 365-administratörs behörighet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="17b12-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="17b12-123">I det vänstra fönstret, under **administrations Center**, väljer du **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="17b12-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="17b12-124">Om det klassiska administrations centret för SharePoint visas väljer du **öppna det nu** högst upp på sidan för att öppna det nya administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="17b12-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="17b12-125">I det vänstra fönstret i det nya administrations centret för SharePoint väljer du **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="17b12-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="17b12-126">I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="17b12-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="17b12-128">Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="17b12-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="17b12-129">Logga in på https://login.partner.microsoftonline.cn/ som global eller SharePoint-administratör och välj sedan administratörs panelen för att öppna administrations centret.</span><span class="sxs-lookup"><span data-stu-id="17b12-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="17b12-130">(Om du ser ett meddelande om att du inte har behörighet att komma åt sidan innebär det att du inte har Microsoft 365-administratörs behörighet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="17b12-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="17b12-131">I det vänstra fönstret, under **administrations Center**, väljer du **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="17b12-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="17b12-132">Om det klassiska administrations centret för SharePoint visas väljer du **öppna det nu** högst upp på sidan för att öppna det nya administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="17b12-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="17b12-133">I det vänstra fönstret i det nya administrations centret för SharePoint väljer du **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="17b12-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="17b12-134">I det övre högra hörnet på sidan kan du se hur mycket lagrings utrymme som används för alla webbplatser och det totala lagrings utrymmet för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="17b12-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Fältet lagring på sidan aktiva webbplatser](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="17b12-136">Det lagrings utrymme som används inkluderar inte ändringar gjorda inom de senaste 24-48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="17b12-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="17b12-p111">När du har fastställt hur mycket lagringsutrymme du använder kan du lägga till eller ta bort lagringsutrymme för din prenumeration. Följ stegen i den här artikeln om du vill ta reda på hur mycket det kostar att lägga till lagringsutrymme och kontrollera prisinformationen innan köpet.</span><span class="sxs-lookup"><span data-stu-id="17b12-p111">After you've determined how much storage you're using, you can add or remove storage space for your subscription. To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="17b12-139">Information om hur du anger lagringsgränser för webbplatssamlingar finns i [Hantera lagringsgränser för webbplatssamlingar](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="17b12-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="17b12-140">Lägga till lagrings utrymme i din prenumeration</span><span class="sxs-lookup"><span data-stu-id="17b12-140">Add storage to your subscription</span></span>

<span data-ttu-id="17b12-141">Om du ännu inte har köpt ett extra lagrings utrymme för din prenumeration kan du göra det.</span><span class="sxs-lookup"><span data-stu-id="17b12-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17b12-142">Gå till sidan fakturering i administrations centret **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> .</span><span class="sxs-lookup"><span data-stu-id="17b12-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="17b12-143">Välj **tillägg**längst ned på sidan **Köp tjänster** .</span><span class="sxs-lookup"><span data-stu-id="17b12-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="17b12-144">Välj **Office 365 extra fil lagring**.</span><span class="sxs-lookup"><span data-stu-id="17b12-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="17b12-145">På sidan **Office 365 extra File Storage** , om visas väljer du bas abonnemang och anger sedan det antal gigabyte av lagrings utrymme som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="17b12-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="17b12-146">Välj **kolla ut nu**.</span><span class="sxs-lookup"><span data-stu-id="17b12-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="17b12-147">Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**</span><span class="sxs-lookup"><span data-stu-id="17b12-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="17b12-148">På sidan **Complete order** kontrollerar du summan.</span><span class="sxs-lookup"><span data-stu-id="17b12-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="17b12-149">Om du behöver göra några ändringar väljer du **Redigera order**.</span><span class="sxs-lookup"><span data-stu-id="17b12-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="17b12-150">Om ordern kräver en kredit kontroll markerar du kryss rutan.</span><span class="sxs-lookup"><span data-stu-id="17b12-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="17b12-151">När du är klar väljer du **Placera order** \> **gå till administratörens start sida**.</span><span class="sxs-lookup"><span data-stu-id="17b12-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17b12-152">Gå till sidan **faktura** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">prenumerationer</a> i administrations centret.  </span><span class="sxs-lookup"><span data-stu-id="17b12-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="17b12-153">På sidan **prenumerationer** väljer du den prenumeration där du vill lägga till lagrings utrymme och väljer sedan **tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17b12-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="17b12-155">Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="17b12-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="17b12-156">Välj **köp tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17b12-156">Select **Buy add-ons**.</span></span>

    ![Länken Köp tilläggs komponenter på sidan prenumerationer i administrations centret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="17b12-158">På sidan **Köp tjänster** pekar du på eller trycker på **Office 365 extra fil lagring**och väljer sedan **Köp nu**.</span><span class="sxs-lookup"><span data-stu-id="17b12-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="17b12-159">Ange antalet användar licenser du behöver och välj en bas prenumeration om det visas.</span><span class="sxs-lookup"><span data-stu-id="17b12-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="17b12-160">Välj **kolla ut nu**.</span><span class="sxs-lookup"><span data-stu-id="17b12-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="17b12-161">Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**</span><span class="sxs-lookup"><span data-stu-id="17b12-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="17b12-162">På sidan **Complete order** väljer du **Lägg order**.</span><span class="sxs-lookup"><span data-stu-id="17b12-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="17b12-163">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="17b12-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="17b12-164">På sidan **prenumerationer** väljer du den prenumeration där du vill lägga till lagrings utrymme och väljer sedan **tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17b12-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="17b12-166">Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="17b12-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="17b12-167">Välj **köp tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17b12-167">Select **Buy add-ons**.</span></span>

    ![Länken Köp tilläggs komponenter på sidan prenumerationer i administrations centret.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="17b12-169">På sidan **Köp tjänster** pekar du på eller trycker på **Office 365 extra fil lagring**och väljer sedan **Köp nu**.</span><span class="sxs-lookup"><span data-stu-id="17b12-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="17b12-170">Ange antalet användar licenser du behöver och välj en bas prenumeration om det visas.</span><span class="sxs-lookup"><span data-stu-id="17b12-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="17b12-171">Välj **kolla ut nu**.</span><span class="sxs-lookup"><span data-stu-id="17b12-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="17b12-172">Kontrol lera hur många GB lagrings utrymme du har valt på sidan **Hur ser det ut?** **.**</span><span class="sxs-lookup"><span data-stu-id="17b12-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="17b12-173">På sidan **Complete order** väljer du **Lägg order**.</span><span class="sxs-lookup"><span data-stu-id="17b12-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="17b12-174">Öka eller minska lagringsutrymme</span><span class="sxs-lookup"><span data-stu-id="17b12-174">Increase or decrease storage</span></span>

<span data-ttu-id="17b12-175">Om du redan har köpt extra fil lagrings utrymme via **Office 365 extra File Storage** -tillägget kan du öka eller minska det extra lagrings utrymmet för ditt abonnemang genom att använda de här stegen.</span><span class="sxs-lookup"><span data-stu-id="17b12-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="17b12-176">Du kan minska lagrings utrymmet till så lite som 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="17b12-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="17b12-177">[Kontakta supporten](../admin/contact-support-for-business-products.md)om du vill ta bort allt extra lagrings utrymme.</span><span class="sxs-lookup"><span data-stu-id="17b12-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17b12-178">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="17b12-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="17b12-179">På fliken **produkter** väljer du den prenumeration som innehåller tillägget **Office 365 extra fil lagring** .</span><span class="sxs-lookup"><span data-stu-id="17b12-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="17b12-180">På sidan Product details går du **till avsnittet tillägg** och väljer **Hantera tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17b12-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="17b12-181">I fönstret **Hantera tillägg** väljer du **Office 365 extra fil lagring**i listan **tillägg** .</span><span class="sxs-lookup"><span data-stu-id="17b12-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="17b12-182">I text rutan **kvantitet** anger du antalet GBS som du vill använda för abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="17b12-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="17b12-183">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="17b12-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17b12-184">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="17b12-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="17b12-185">Välj **tillägg**på sidan **prenumerationer** .</span><span class="sxs-lookup"><span data-stu-id="17b12-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="17b12-187">Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="17b12-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="17b12-188">Under **Office 365 extra fil lagring**väljer du **ändra antal**.</span><span class="sxs-lookup"><span data-stu-id="17b12-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="17b12-190">I det högra fönstret anger du det totala antalet gigabyte du behöver och väljer sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="17b12-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="17b12-191">Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.</span><span class="sxs-lookup"><span data-stu-id="17b12-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="17b12-192">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="17b12-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="17b12-193">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="17b12-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="17b12-194">Välj **tillägg**på sidan **prenumerationer** .</span><span class="sxs-lookup"><span data-stu-id="17b12-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="17b12-196">Om du inte ser **tillägg**och prenumerationen har köpts via en partner väljer du **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="17b12-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="17b12-197">Under **Office 365 extra fil lagring**väljer du **ändra antal**.</span><span class="sxs-lookup"><span data-stu-id="17b12-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Länken Ändra antal.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="17b12-199">I det högra fönstret anger du det totala antalet gigabyte du behöver och väljer sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="17b12-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="17b12-200">Om du för närvarande till exempel har 200 GB extra lagringsutrymme men bara behöver 100 GB ska du ange **100** i rutan.</span><span class="sxs-lookup"><span data-stu-id="17b12-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="17b12-201">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="17b12-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="17b12-202">Berättigar mitt abonnemang till Office 365 extra fillagring?</span><span class="sxs-lookup"><span data-stu-id="17b12-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="17b12-203">Office 365 extra fillagring är tillgängligt för följande prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="17b12-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="17b12-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="17b12-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="17b12-205">Office 365 Enterprise, E2</span><span class="sxs-lookup"><span data-stu-id="17b12-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="17b12-206">Office 365 Enterprise, E3</span><span class="sxs-lookup"><span data-stu-id="17b12-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="17b12-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="17b12-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="17b12-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="17b12-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="17b12-209">Office för webben med SharePoint abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="17b12-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="17b12-210">Office för webben med SharePoint abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="17b12-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="17b12-211">SharePoint Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="17b12-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="17b12-212">SharePoint Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="17b12-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="17b12-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="17b12-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="17b12-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="17b12-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="17b12-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="17b12-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="17b12-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="17b12-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="17b12-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="17b12-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="17b12-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="17b12-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="17b12-219">Office 365 extra fil lagring är också tillgängligt för GCC-, GCC-och DOD-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="17b12-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="17b12-220">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="17b12-220">Related content</span></span>

<span data-ttu-id="17b12-221">[Hantera lagrings gränser för webbplatser](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel) </span><span class="sxs-lookup"><span data-stu-id="17b12-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="17b12-222">[Ange standard lagrings utrymme för OneDrive-användare](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="17b12-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
