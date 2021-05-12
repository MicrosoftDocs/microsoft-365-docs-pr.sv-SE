---
title: Avsluta ditt konto
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Lär dig hur du stänger ditt konto hos Microsoft.
ms.date: 04/02/2021
ms.openlocfilehash: 767a82088500bc24c0d4755a2dafd40742fc796c
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331772"
---
# <a name="close-your-account"></a><span data-ttu-id="ba861-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="ba861-103">Close your account</span></span>

<span data-ttu-id="ba861-104">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="ba861-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="ba861-105">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="ba861-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ba861-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="ba861-106">Before you begin</span></span>

<span data-ttu-id="ba861-107">Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.</span><span class="sxs-lookup"><span data-stu-id="ba861-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="ba861-108">Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ba861-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="ba861-109">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ba861-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="ba861-110">Steg 1: Ta bort användare</span><span class="sxs-lookup"><span data-stu-id="ba861-110">Step 1: Delete users</span></span>

<span data-ttu-id="ba861-111">Ta bort alla användare utom en global administratör.</span><span class="sxs-lookup"><span data-stu-id="ba861-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="ba861-112">Den globala administratören slutför stegen för att stänga kontot.</span><span class="sxs-lookup"><span data-stu-id="ba861-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="ba861-113">Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="ba861-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="ba861-114">Om användarna synkroniseras från en lokal miljö inaktiverar du först synkroniseringen och tar sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ba861-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="ba861-115">Information om hur du tar bort användare [finns i Användarhanteringsadministratör: Ta bort en eller flera användare](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span><span class="sxs-lookup"><span data-stu-id="ba861-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="ba861-116">Du kan också använda [PowerShell-cmdleten Remove-MsolUser](/powershell/module/msonline/remove-msoluser) för att massborttagning av användare.</span><span class="sxs-lookup"><span data-stu-id="ba861-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="ba861-117">Om din organisation använder Active Directory som synkroniserar med Microsoft Azure Active Directory (Azure AD) ska du ta bort användarkontot från Active Directory i stället.</span><span class="sxs-lookup"><span data-stu-id="ba861-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="ba861-118">Instruktioner finns i [Massborttagning av användare i Azure Active Directory.](/azure/active-directory/users-groups-roles/users-bulk-delete)</span><span class="sxs-lookup"><span data-stu-id="ba861-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="ba861-119">Steg 2: Avbryt alla aktiva prenumerationer</span><span class="sxs-lookup"><span data-stu-id="ba861-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="ba861-120">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="ba861-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ba861-121">På fliken **Produkter** hittar du en aktiv prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ba861-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="ba861-122">Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="ba861-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="ba861-123">I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="ba861-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="ba861-124">Alternativt kan du ge valfri feedback.</span><span class="sxs-lookup"><span data-stu-id="ba861-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="ba861-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ba861-125">Select **Save**.</span></span>
5. <span data-ttu-id="ba861-126">Upprepa steg 1 till 4 för att avbryta alla aktiva prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ba861-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="ba861-127">Steg 3: Ta bort alla inaktiverade prenumerationer</span><span class="sxs-lookup"><span data-stu-id="ba861-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="ba861-128">I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="ba861-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ba861-129">Välj en **inaktiverad** prenumeration på fliken Produkter.</span><span class="sxs-lookup"><span data-stu-id="ba861-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="ba861-130">Välj Ta bort prenumeration i avsnittet **Prenumerations- och betalningsinställningar** på sidan **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="ba861-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="ba861-131">I fönstret **Ta bort prenumeration** väljer du Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="ba861-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="ba861-132">Välj **Ja i** dialogrutan Ta bort **prenumeration.**</span><span class="sxs-lookup"><span data-stu-id="ba861-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="ba861-133">Upprepa steg 3 till 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="ba861-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="ba861-134">Om du inte kan ta bort en inaktiverad prenumeration direkt kontaktar [du support.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="ba861-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="ba861-135">Steg 4: Inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="ba861-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="ba861-136">Logga in på administrationscentret med ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="ba861-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="ba861-137">Du kan kontrollera vilka roller du har i [Kontrollera administratörsroller i din organisation.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="ba861-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="ba861-138">Gå till **sidan Användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva</a> användare.</span><span class="sxs-lookup"><span data-stu-id="ba861-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="ba861-139">Välj **Multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="ba861-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="ba861-140">På sidan Multifaktorautentisering inaktiverar du alla konton utom för det globala administratörskonto som du använder för närvarande.</span><span class="sxs-lookup"><span data-stu-id="ba861-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="ba861-141">Du kan också [använda PowerShell för att inaktivera multifaktorautentisering för flera användare.](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="ba861-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="ba861-142">Steg 5: Ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ba861-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="ba861-143">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrationscentret för Azure AD med</a> ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="ba861-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="ba861-144">Välj **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="ba861-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ba861-145">Växla till den organisation som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="ba861-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="ba861-146">Välj **Ta bort klientorganisation.**</span><span class="sxs-lookup"><span data-stu-id="ba861-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="ba861-147">Om din organisation misslyckas med en eller flera kontroller visas en länk till mer information om hur du gör för att överföra kontrollerna.</span><span class="sxs-lookup"><span data-stu-id="ba861-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="ba861-148">När du har slutfört alla kontroller väljer **du Ta** bort för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="ba861-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="ba861-149">När du är klar med det här sista steget stängs ditt konto hos Microsoft och tas bort.</span><span class="sxs-lookup"><span data-stu-id="ba861-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
