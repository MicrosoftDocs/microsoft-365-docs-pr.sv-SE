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
ms.openlocfilehash: 0ee0a649a9adb93ecdbb1cd9dbedbc04dfb46ba0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579752"
---
# <a name="close-your-account"></a><span data-ttu-id="b46a3-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="b46a3-103">Close your account</span></span>

<span data-ttu-id="b46a3-104">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="b46a3-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="b46a3-105">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="b46a3-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b46a3-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b46a3-106">Before you begin</span></span>

<span data-ttu-id="b46a3-107">Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.</span><span class="sxs-lookup"><span data-stu-id="b46a3-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="b46a3-108">Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b46a3-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="b46a3-109">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b46a3-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="b46a3-110">Steg 1: Ta bort användare</span><span class="sxs-lookup"><span data-stu-id="b46a3-110">Step 1: Delete users</span></span>

<span data-ttu-id="b46a3-111">Ta bort alla användare utom en global administratör.</span><span class="sxs-lookup"><span data-stu-id="b46a3-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="b46a3-112">Den globala administratören slutför stegen för att stänga kontot.</span><span class="sxs-lookup"><span data-stu-id="b46a3-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="b46a3-113">Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="b46a3-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="b46a3-114">Om användarna synkroniseras från en lokal miljö inaktiverar du först synkroniseringen och tar sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b46a3-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="b46a3-115">Information om hur du tar bort användare <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">finns i Användarhanteringsadministratör: Ta bort en eller flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="b46a3-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="b46a3-116">Du kan också använda <a href="https://go.microsoft.com/fwlink/?linkid=842230">PowerShell-cmdleten Remove-MsolUser</a> för att massborttagning av användare.</span><span class="sxs-lookup"><span data-stu-id="b46a3-116">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="b46a3-117">Om din organisation använder Active Directory som synkroniserar med Microsoft Azure Active Directory (Azure AD) ska du ta bort användarkontot från Active Directory i stället.</span><span class="sxs-lookup"><span data-stu-id="b46a3-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="b46a3-118">Instruktioner finns i <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Massborttagning av användare i Azure Active Directory.</a></span><span class="sxs-lookup"><span data-stu-id="b46a3-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="b46a3-119">Steg 2: Avbryt alla aktiva prenumerationer</span><span class="sxs-lookup"><span data-stu-id="b46a3-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="b46a3-120">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="b46a3-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b46a3-121">På fliken **Produkter** hittar du en aktiv prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b46a3-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="b46a3-122">Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="b46a3-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="b46a3-123">I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b46a3-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="b46a3-124">Alternativt kan du ge valfri feedback.</span><span class="sxs-lookup"><span data-stu-id="b46a3-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="b46a3-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b46a3-125">Select **Save**.</span></span>
5. <span data-ttu-id="b46a3-126">Upprepa steg 1 till 4 för att avbryta alla aktiva prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="b46a3-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="b46a3-127">Steg 3: Ta bort alla inaktiverade prenumerationer</span><span class="sxs-lookup"><span data-stu-id="b46a3-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="b46a3-128">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="b46a3-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b46a3-129">Välj en **inaktiverad** prenumeration på fliken Produkter.</span><span class="sxs-lookup"><span data-stu-id="b46a3-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="b46a3-130">Välj Ta bort prenumeration i avsnittet **Prenumerations- och betalningsinställningar** på sidan **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="b46a3-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="b46a3-131">I fönstret **Ta bort prenumeration** väljer du Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="b46a3-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="b46a3-132">Välj **Ja i** dialogrutan Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="b46a3-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="b46a3-133">Upprepa steg 3 till 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="b46a3-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b46a3-134">Om du inte kan ta bort en inaktiverad prenumeration direkt kontaktar <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">du supporten</a></span><span class="sxs-lookup"><span data-stu-id="b46a3-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="b46a3-135">Steg 4: Inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="b46a3-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="b46a3-136">Logga in på administrationscentret med ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b46a3-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="b46a3-137">Du kan kontrollera vilka roller du har i [Kontrollera administratörsroller i din organisation.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="b46a3-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="b46a3-138">Gå till **sidan Användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva</a> användare.</span><span class="sxs-lookup"><span data-stu-id="b46a3-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="b46a3-139">Välj **Multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="b46a3-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="b46a3-140">På sidan Multifaktorautentisering inaktiverar du alla konton utom för det globala administratörskonto som du använder för närvarande.</span><span class="sxs-lookup"><span data-stu-id="b46a3-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="b46a3-141">Du kan också <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare.</a></span><span class="sxs-lookup"><span data-stu-id="b46a3-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="b46a3-142">Steg 5: Ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b46a3-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="b46a3-143">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrationscentret för Azure AD med</a> ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b46a3-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="b46a3-144">Välj **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="b46a3-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b46a3-145">Växla till den organisation som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="b46a3-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="b46a3-146">Välj **Ta bort klientorganisation.**</span><span class="sxs-lookup"><span data-stu-id="b46a3-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="b46a3-147">Om din organisation misslyckas med en eller flera kontroller visas en länk till mer information om hur du gör för att överföra kontrollerna.</span><span class="sxs-lookup"><span data-stu-id="b46a3-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="b46a3-148">När du har slutfört alla kontroller väljer **du Ta** bort för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="b46a3-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="b46a3-149">När du är klar med det här sista steget stängs ditt konto hos Microsoft och tas bort.</span><span class="sxs-lookup"><span data-stu-id="b46a3-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>