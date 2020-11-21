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
description: Lär dig hur du avslutar ditt konto hos Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376323"
---
# <a name="close-your-account"></a><span data-ttu-id="22a09-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="22a09-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="22a09-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="22a09-104">The admin center is changing.</span></span> <span data-ttu-id="22a09-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="22a09-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="22a09-106">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="22a09-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="22a09-107">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="22a09-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="22a09-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="22a09-108">Before you begin</span></span>

<span data-ttu-id="22a09-109">Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.</span><span class="sxs-lookup"><span data-stu-id="22a09-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="22a09-110">Du måste vara global eller fakturerings administratör för att kunna utföra åtgärderna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="22a09-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="22a09-111">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="22a09-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="22a09-112">Steg 1: ta bort användare</span><span class="sxs-lookup"><span data-stu-id="22a09-112">Step 1: Delete users</span></span>

<span data-ttu-id="22a09-113">Ta bort alla användare utom den globala administratören.</span><span class="sxs-lookup"><span data-stu-id="22a09-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="22a09-114">Den globala administratören Slutför stegen för att avsluta kontot.</span><span class="sxs-lookup"><span data-stu-id="22a09-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="22a09-115">Innan du kan ta bort katalogen i slutet av processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="22a09-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="22a09-116">Om användare synkroniseras från lokal avaktiverar du först synkronisering och tar sedan bort användarna i moln katalogen genom att använda cmdlets för Azure-portalen eller Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22a09-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="22a09-117">Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">användar hanterings administratör: ta bort en eller flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="22a09-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="22a09-118">Du kan också använda PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdleten Remove-MsolUser</a> för att ta bort användare i bulk.</span><span class="sxs-lookup"><span data-stu-id="22a09-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="22a09-119">Om din organisation använder Active Directory som synkroniseras med Microsoft Azure Active Directory (Azure AD) tar du bort användar kontot från Active Directory i stället.</span><span class="sxs-lookup"><span data-stu-id="22a09-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="22a09-120">Anvisningar finns i <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Mass borttagning av användare i Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="22a09-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="22a09-121">Steg 2: Avbryt alla aktiva abonnemang</span><span class="sxs-lookup"><span data-stu-id="22a09-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="22a09-122">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="22a09-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="22a09-123">Hitta en aktiv prenumeration på fliken **produkter** .</span><span class="sxs-lookup"><span data-stu-id="22a09-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="22a09-124">Välj **fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="22a09-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="22a09-125">I fönstret **Avsluta prenumeration** väljer du en orsak till varför du avbryter.</span><span class="sxs-lookup"><span data-stu-id="22a09-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="22a09-126">Du kan också lämna feedback.</span><span class="sxs-lookup"><span data-stu-id="22a09-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="22a09-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="22a09-127">Select **Save**.</span></span>
5. <span data-ttu-id="22a09-128">Upprepa steg 1 till 4 för att avbryta alla aktiva abonnemang.</span><span class="sxs-lookup"><span data-stu-id="22a09-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="22a09-129">Steg 3: ta bort alla inaktiverade abonnemang</span><span class="sxs-lookup"><span data-stu-id="22a09-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="22a09-130">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="22a09-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="22a09-131">Välj ett inaktiverat abonnemang på fliken **Products** .</span><span class="sxs-lookup"><span data-stu-id="22a09-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="22a09-132">På sidan prenumerations information, under **prenumerations-och betalnings inställningar** väljer du **ta bort abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="22a09-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="22a09-133">Välj **ta bort prenumeration** i fönstret **ta bort prenumeration** .</span><span class="sxs-lookup"><span data-stu-id="22a09-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="22a09-134">I dialog rutan **ta bort prenumeration** väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="22a09-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="22a09-135">För varje inaktive rad prenumeration upprepar du steg 3 till 5 tills alla abonnemang tas bort.</span><span class="sxs-lookup"><span data-stu-id="22a09-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="22a09-136">Om du inte kan ta bort en inaktive rad prenumeration omedelbart <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">kontaktar du supporten</a></span><span class="sxs-lookup"><span data-stu-id="22a09-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="22a09-137">Steg 4: inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="22a09-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="22a09-138">Logga in i administrations centret med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="22a09-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="22a09-139">Information om hur du kontrollerar vilka roller du har finns i [kontrol lera administratörs roller i organisationen](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="22a09-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="22a09-140">Gå till sidan **användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva användare</a> .</span><span class="sxs-lookup"><span data-stu-id="22a09-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="22a09-141">Välj **multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="22a09-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="22a09-142">På sidan multifaktorautentisering avaktiverar du alla konton förutom det globala administratörs konto som du använder för närvarande.</span><span class="sxs-lookup"><span data-stu-id="22a09-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="22a09-143">Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="22a09-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="22a09-144">Steg 5: ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="22a09-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="22a09-145">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrations centret för Azure AD</a> med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="22a09-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="22a09-146">Välj **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="22a09-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="22a09-147">Växla till den organisation som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="22a09-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="22a09-148">Välj **ta bort klient organisation**.</span><span class="sxs-lookup"><span data-stu-id="22a09-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="22a09-149">Om din organisation inte klarar en eller flera kontroller ser du en länk till mer information om hur du överför checkarna.</span><span class="sxs-lookup"><span data-stu-id="22a09-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="22a09-150">När du har överfört alla kontrollerna väljer du **ta bort** för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="22a09-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="22a09-151">När du är klar med det här steget stängs och raderas ditt konto med Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22a09-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>