---
title: Avsluta ditt konto
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Lär dig hur du stänger ditt konto hos Microsoft.
ms.openlocfilehash: 19e9a92a90f7c88cc150844ab451bc71d63e4c4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911668"
---
# <a name="close-your-account"></a><span data-ttu-id="b21e0-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="b21e0-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b21e0-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="b21e0-104">The admin center is changing.</span></span> <span data-ttu-id="b21e0-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b21e0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b21e0-106">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="b21e0-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="b21e0-107">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="b21e0-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b21e0-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b21e0-108">Before you begin</span></span>

<span data-ttu-id="b21e0-109">Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.</span><span class="sxs-lookup"><span data-stu-id="b21e0-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="b21e0-110">Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b21e0-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="b21e0-111">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b21e0-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="b21e0-112">Steg 1: Ta bort användare</span><span class="sxs-lookup"><span data-stu-id="b21e0-112">Step 1: Delete users</span></span>

<span data-ttu-id="b21e0-113">Ta bort alla användare utom en global administratör.</span><span class="sxs-lookup"><span data-stu-id="b21e0-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="b21e0-114">Den globala administratören slutför stegen för att stänga kontot.</span><span class="sxs-lookup"><span data-stu-id="b21e0-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="b21e0-115">Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="b21e0-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="b21e0-116">Om användarna synkroniseras från en lokal miljö inaktiverar du först synkroniseringen och tar sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b21e0-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="b21e0-117">Information om hur du tar bort användare <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">finns i Användarhanteringsadministratör: Ta bort en eller flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="b21e0-117">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="b21e0-118">Du kan också använda <a href="https://go.microsoft.com/fwlink/?linkid=842230">PowerShell-cmdleten Remove-MsolUser</a> för att massborttagning av användare.</span><span class="sxs-lookup"><span data-stu-id="b21e0-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="b21e0-119">Om din organisation använder Active Directory som synkroniserar med Microsoft Azure Active Directory (Azure AD) ska du ta bort användarkontot från Active Directory i stället.</span><span class="sxs-lookup"><span data-stu-id="b21e0-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="b21e0-120">Instruktioner finns i <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Massborttagning av användare i Azure Active Directory.</a></span><span class="sxs-lookup"><span data-stu-id="b21e0-120">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="b21e0-121">Steg 2: Avbryt alla aktiva prenumerationer</span><span class="sxs-lookup"><span data-stu-id="b21e0-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="b21e0-122">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="b21e0-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b21e0-123">På fliken **Produkter** hittar du en aktiv prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b21e0-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="b21e0-124">Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="b21e0-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="b21e0-125">I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b21e0-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="b21e0-126">Alternativt kan du ge valfri feedback.</span><span class="sxs-lookup"><span data-stu-id="b21e0-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="b21e0-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b21e0-127">Select **Save**.</span></span>
5. <span data-ttu-id="b21e0-128">Upprepa steg 1 till 4 för att avbryta alla aktiva prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="b21e0-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="b21e0-129">Steg 3: Ta bort alla inaktiverade prenumerationer</span><span class="sxs-lookup"><span data-stu-id="b21e0-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="b21e0-130">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="b21e0-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b21e0-131">Välj en **inaktiverad** prenumeration på fliken Produkter.</span><span class="sxs-lookup"><span data-stu-id="b21e0-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="b21e0-132">Välj Ta bort prenumeration i avsnittet **Prenumerations- och betalningsinställningar** på sidan **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="b21e0-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="b21e0-133">I fönstret **Ta bort prenumeration** väljer du Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="b21e0-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="b21e0-134">Välj **Ja i** dialogrutan Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="b21e0-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="b21e0-135">Upprepa steg 3 till 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="b21e0-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b21e0-136">Om du inte kan ta bort en inaktiverad prenumeration direkt kontaktar <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">du supporten</a></span><span class="sxs-lookup"><span data-stu-id="b21e0-136">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="b21e0-137">Steg 4: Inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="b21e0-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="b21e0-138">Logga in på administrationscentret med ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b21e0-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="b21e0-139">Du kan kontrollera vilka roller du har i [Kontrollera administratörsroller i din organisation.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="b21e0-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="b21e0-140">Gå till **sidan Användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva</a> användare.</span><span class="sxs-lookup"><span data-stu-id="b21e0-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="b21e0-141">Välj **Multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="b21e0-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="b21e0-142">På sidan Multifaktorautentisering inaktiverar du alla konton utom för det globala administratörskonto som du använder för närvarande.</span><span class="sxs-lookup"><span data-stu-id="b21e0-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="b21e0-143">Du kan också <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare.</a></span><span class="sxs-lookup"><span data-stu-id="b21e0-143">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="b21e0-144">Steg 5: Ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b21e0-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="b21e0-145">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrationscentret för Azure AD med</a> ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b21e0-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="b21e0-146">Välj **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="b21e0-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b21e0-147">Växla till den organisation som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="b21e0-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="b21e0-148">Välj **Ta bort klientorganisation.**</span><span class="sxs-lookup"><span data-stu-id="b21e0-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="b21e0-149">Om din organisation misslyckas med en eller flera kontroller visas en länk till mer information om hur du gör för att överföra kontrollerna.</span><span class="sxs-lookup"><span data-stu-id="b21e0-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="b21e0-150">När du har slutfört alla kontroller väljer **du Ta** bort för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="b21e0-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="b21e0-151">När du är klar med det här sista steget stängs ditt konto hos Microsoft och tas bort.</span><span class="sxs-lookup"><span data-stu-id="b21e0-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>