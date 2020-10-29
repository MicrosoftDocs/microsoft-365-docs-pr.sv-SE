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
ms.openlocfilehash: 0fed7df54a21b3696e81915af78e377e855bfd12
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794903"
---
# <a name="close-your-account"></a><span data-ttu-id="156aa-103">Avsluta ditt konto</span><span class="sxs-lookup"><span data-stu-id="156aa-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="156aa-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="156aa-104">The admin center is changing.</span></span> <span data-ttu-id="156aa-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="156aa-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="156aa-106">När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="156aa-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="156aa-107">Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.</span><span class="sxs-lookup"><span data-stu-id="156aa-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="156aa-108">Innan du börjar kan du se till att säkerhetskopiera alla data du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="156aa-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="156aa-109">Steg 1: ta bort användare</span><span class="sxs-lookup"><span data-stu-id="156aa-109">Step 1: Delete users</span></span>

<span data-ttu-id="156aa-110">Ta bort alla användare utom den globala administratören som slutför stegen för att avsluta kontot.</span><span class="sxs-lookup"><span data-stu-id="156aa-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="156aa-111">Innan du kan ta bort katalogen i slutet av processen måste du ta bort alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="156aa-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="156aa-112">Om användare synkroniseras från lokal avaktiverar du först synkronisering och tar sedan bort användarna i moln katalogen genom att använda cmdlets för Azure-portalen eller Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="156aa-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="156aa-113">Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">användar hanterings administratör: ta bort en eller flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="156aa-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="156aa-114">Du kan också använda PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdleten Remove-MsolUser</a> för att ta bort användare i bulk.</span><span class="sxs-lookup"><span data-stu-id="156aa-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="156aa-115">Om din organisation använder Active Directory som synkroniserar med Azure AD kan du i stället ta bort användar kontot från Active Directory.</span><span class="sxs-lookup"><span data-stu-id="156aa-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="156aa-116">Anvisningar finns i <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Mass borttagning av användare i Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="156aa-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="156aa-117">Steg 2: Avbryt alla aktiva abonnemang</span><span class="sxs-lookup"><span data-stu-id="156aa-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="156aa-118">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="156aa-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="156aa-119">Om abonnemangs listan är i **tabellvy** väljer du **kort** till höger.</span><span class="sxs-lookup"><span data-stu-id="156aa-119">If the subscriptions list is in **Table** view, on the right, select **Cards** .</span></span>

3. <span data-ttu-id="156aa-120">Sök efter en aktiv prenumeration och välj **Avbryt prenumeration** i avsnittet **Inställningar & åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="156aa-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription** .</span></span>

4. <span data-ttu-id="156aa-121">Följ anvisningarna för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="156aa-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="156aa-122">Upprepa steg 1 till 4 för att avbryta alla aktiva abonnemang.</span><span class="sxs-lookup"><span data-stu-id="156aa-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="156aa-123">Steg 3: ta bort alla inaktiverade abonnemang</span><span class="sxs-lookup"><span data-stu-id="156aa-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="156aa-124">Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .</span><span class="sxs-lookup"><span data-stu-id="156aa-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="156aa-125">Om abonnemangs listan är i **tabellvy** väljer du **kort** till höger.</span><span class="sxs-lookup"><span data-stu-id="156aa-125">If the subscriptions list is in **Table** view, on the right, select **Cards** .</span></span>

3. <span data-ttu-id="156aa-126">Bredvid **prenumerations status** väljer du **inaktive rad** .</span><span class="sxs-lookup"><span data-stu-id="156aa-126">Next to **Subscription status** , select **Disabled** .</span></span>

4. <span data-ttu-id="156aa-127">Hitta en inaktive rad prenumeration och välj **ta bort** i avsnittet **Inställningar & åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="156aa-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete** .</span></span>

5. <span data-ttu-id="156aa-128">I dialog rutan **ta bort prenumeration** markerar du kryss rutan **Jag förstår effekt** och väljer sedan **ta bort abonnemang** .</span><span class="sxs-lookup"><span data-stu-id="156aa-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription** .</span></span>

6. <span data-ttu-id="156aa-129">Upprepa steg 4 och 5 för varje inaktive rad prenumeration tills alla abonnemang har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="156aa-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="156aa-130">Steg 4: inaktivera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="156aa-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="156aa-131">Gå till sidan **användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva användare</a> i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="156aa-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="156aa-132">Välj **multifaktorautentisering** .</span><span class="sxs-lookup"><span data-stu-id="156aa-132">Choose **Multi-factor authentication** .</span></span>

3. <span data-ttu-id="156aa-133">På sidan multifaktorautentisering avaktiverar du alla konton förutom det globala administratörs konto som du använder för närvarande.</span><span class="sxs-lookup"><span data-stu-id="156aa-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="156aa-134">Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.</span><span class="sxs-lookup"><span data-stu-id="156aa-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="156aa-135">Steg 5: ta bort katalogen i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="156aa-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="156aa-136">Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrations centret för Azure AD</a> med ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="156aa-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="156aa-137">Välj **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="156aa-137">Select **Azure Active Directory** .</span></span>

3. <span data-ttu-id="156aa-138">Växla till den organisation som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="156aa-138">Switch to the organization you want to delete.</span></span>

4. <span data-ttu-id="156aa-139">Välj **ta bort klient organisation** .</span><span class="sxs-lookup"><span data-stu-id="156aa-139">Select **Delete tenant** .</span></span>

5. <span data-ttu-id="156aa-140">Om din organisation inte klarar en eller flera kontroller ser du en länk till mer information om hur du överför checkarna.</span><span class="sxs-lookup"><span data-stu-id="156aa-140">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="156aa-141">När du har överfört alla kontrollerna väljer du **ta bort** för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="156aa-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="156aa-142">När du är klar med det här steget stängs och raderas ditt konto med Microsoft.</span><span class="sxs-lookup"><span data-stu-id="156aa-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
