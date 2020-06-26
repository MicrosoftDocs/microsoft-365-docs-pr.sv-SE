---
title: Avsluta ditt konto
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Läs om hur du avslutar ditt konto hos Microsoft.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898927"
---
# <a name="close-your-account"></a><span data-ttu-id="d2333-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="d2333-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d2333-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="d2333-104">The admin center is changing.</span></span> <span data-ttu-id="d2333-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d2333-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d2333-106">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="d2333-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="d2333-107">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="d2333-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="d2333-108">Innan du påbörjar den här processen måste du säkerhetskopiera alla data som du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="d2333-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="d2333-109">Steg 1: Ta bort användare</span><span class="sxs-lookup"><span data-stu-id="d2333-109">Step 1: Delete users</span></span>

<span data-ttu-id="d2333-110">Ta bort alla användare utom en global administratör som slutför stegen för att stänga kontot.</span><span class="sxs-lookup"><span data-stu-id="d2333-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="d2333-111">Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="d2333-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="d2333-112">Om användare synkroniseras från lokala, stäng först av synkronisering och ta sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="d2333-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="d2333-113">Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Användarhanteringsadministratör: Ta bort en eller flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="d2333-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="d2333-114">Du kan också använda cmdleten <a href="https://go.microsoft.com/fwlink/?linkid=842230">Ta bort MsolUser</a> PowerShell för att ta bort användare i grupp.</span><span class="sxs-lookup"><span data-stu-id="d2333-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="d2333-115">Om din organisation använder Active Directory som synkroniseras med Azure AD tar du bort användarkontot från Active Directory i stället.</span><span class="sxs-lookup"><span data-stu-id="d2333-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="d2333-116">Instruktioner finns <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">i Massborttagning av användare i Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="d2333-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="d2333-117">Steg 2: Avbryta alla aktiva prenumerationer</span><span class="sxs-lookup"><span data-stu-id="d2333-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="d2333-118">Gå till sidan **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="d2333-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="d2333-119">Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .</span><span class="sxs-lookup"><span data-stu-id="d2333-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="d2333-120">Hitta en aktiv prenumeration och välj **Avbryt prenumeration**i avsnittet Inställningar **& åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="d2333-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="d2333-121">Följ anvisningarna för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="d2333-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="d2333-122">Upprepa steg 1 till och med 4 för att avbryta alla aktiva prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="d2333-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="d2333-123">Steg 3: Ta bort alla inaktiverade prenumerationer</span><span class="sxs-lookup"><span data-stu-id="d2333-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="d2333-124">Gå till sidan **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="d2333-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="d2333-125">Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .</span><span class="sxs-lookup"><span data-stu-id="d2333-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="d2333-126">Välj **Inaktiverad bredvid** **Prenumerationsstatus**.</span><span class="sxs-lookup"><span data-stu-id="d2333-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="d2333-127">Hitta en inaktiverad prenumeration och välj **Ta bort**i avsnittet Inställningar **& åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="d2333-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="d2333-128">Markera kryssrutan **Jag förstår fliken Påverkan i** dialogrutan Ta bort **prenumeration** och välj sedan Ta **bort prenumeration**.</span><span class="sxs-lookup"><span data-stu-id="d2333-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="d2333-129">Upprepa steg 4 och 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="d2333-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="d2333-130">Steg 4: Inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="d2333-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="d2333-131">Gå till sidan Aktiva användare i **administrationscentret.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a></span><span class="sxs-lookup"><span data-stu-id="d2333-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d2333-132">Välj **Multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="d2333-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="d2333-133">På sidan multifaktorautentisering inaktiverar du alla konton utom det globala administratörskonto som du för närvarande använder.</span><span class="sxs-lookup"><span data-stu-id="d2333-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="d2333-134">Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="d2333-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="d2333-135">Steg 5: Ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d2333-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="d2333-136">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-administrationscentret</a> med ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="d2333-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="d2333-137">Välj **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d2333-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="d2333-138">Växla till den katalog som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="d2333-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="d2333-139">Välj **Ta bort katalog**.</span><span class="sxs-lookup"><span data-stu-id="d2333-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="d2333-140">Om katalogen misslyckas med en eller flera kontroller visas en länk till mer information om hur du skickar kontrollerna.</span><span class="sxs-lookup"><span data-stu-id="d2333-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="d2333-141">När du har klarat alla kontroller väljer du **Ta bort** för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="d2333-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="d2333-142">När du har slutfört det här sista steget stängs kontot hos Microsoft och tas bort.</span><span class="sxs-lookup"><span data-stu-id="d2333-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
