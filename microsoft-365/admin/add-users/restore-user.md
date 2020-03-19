---
title: Återställa en användare i Office 365
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Lär dig hur du återställer borttagna Office 365-användarkonton och alla associerade data.
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808681"
---
# <a name="restore-a-user-in-office-365"></a><span data-ttu-id="8c428-103">Återställa en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="8c428-103">Restore a user in Office 365</span></span>
   
<span data-ttu-id="8c428-p101">Om du återställer ett användarkonto inom 30 dagar från det att det togs bort, återställs kontot och alla associerade data. Användaren kan logga in med samma arbets- eller skolkonto. Postlådan återställs i sin helhet. Om du vill ta reda på hur mycket tid som återstår innan ett visst användarkonto inte längre kan återställas [kontaktar du oss](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="8c428-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="8c428-108">Här är några tips:</span><span class="sxs-lookup"><span data-stu-id="8c428-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="8c428-109">Se till att det finns tillgängliga Office 365-licenser som du kan tilldela kontot.</span><span class="sxs-lookup"><span data-stu-id="8c428-109">Make sure there are Office 365 licenses available that you can assign to the account.</span></span>
    
- <span data-ttu-id="8c428-110">Om ditt företag använder Active Directory, se [Felsökning av borttagna konton i Office 365](https://support.microsoft.com/kb/2619308) för instruktioner om återställning av användarkonton.</span><span class="sxs-lookup"><span data-stu-id="8c428-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="8c428-111">Återställa ett eller flera användarkonton</span><span class="sxs-lookup"><span data-stu-id="8c428-111">Restore one or more user accounts</span></span>

<span data-ttu-id="8c428-112">Du måste vara global administratör eller användarhanteringsadministratör i Office 365 för att kunna göra så här.</span><span class="sxs-lookup"><span data-stu-id="8c428-112">You must be a global admin or user management admin in Office 365 to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8c428-113">Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8c428-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8c428-114">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-114">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8c428-115">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-115">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="8c428-116">På sidan **Borttagna användare** väljer du namnen på de användare som du vill återställa och väljer sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-116">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="8c428-117">Följ anvisningarna för att ange deras lösenord och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-117">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="8c428-118">Om användaren har återställts väljer du **Skicka e-post och stäng**.</span><span class="sxs-lookup"><span data-stu-id="8c428-118">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="8c428-119">Om det uppstår en namnkonflikt eller en proxyadresskonflikt kan du läsa instruktionerna nedan om återställning av dessa konton.</span><span class="sxs-lookup"><span data-stu-id="8c428-119">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="8c428-120">När du har återställt en användare kontrollerar du att du meddelar dem att deras lösenord har ändrats och att du följer upp med dem.</span><span class="sxs-lookup"><span data-stu-id="8c428-120">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="8c428-121">Återställa en användare som har en användarnamnskonflikt</span><span class="sxs-lookup"><span data-stu-id="8c428-121">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="8c428-122"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="8c428-122"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="8c428-123">En användarnamnskonflikt inträffar när du tar bort ett användarkonto, skapar ett nytt användarkonto med samma användarnamn (antingen för samma användare eller för en annan användare med ett liknande namn) och sedan försöker återställa det borttagna kontot.</span><span class="sxs-lookup"><span data-stu-id="8c428-123">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="8c428-p103">Om du vill lösa detta ersätter du det aktiva användarkontot med det konto som du återställer. Eller tilldela det konto som du återställer ett annat användarnamn, så att inte båda kontona har samma användarnamn. Följ nedanstående anvisningar.</span><span class="sxs-lookup"><span data-stu-id="8c428-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8c428-127">Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8c428-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8c428-128">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-128">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8c428-129">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-129">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="8c428-130">På sidan **Borttagna användare** markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-130">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8c428-p104">Om återställandet av två eller fler användare misslyckas visas ett felmeddelande som informerar dig om att återställningsåtgärden misslyckades för vissa användare. Ta fram loggen och kontrollera vilka användare som inte återställdes. Dessa konton måste du återställa ett åt gången.</span><span class="sxs-lookup"><span data-stu-id="8c428-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="8c428-133">Följ anvisningarna för att ange lösenordet och välj **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-133">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="8c428-p105">Ett meddelande dyker upp där det står att det inte gick att återställa kontot. Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="8c428-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="8c428-p106">Avbryt återställningen och byt namn på den aktiva användaren. Försök sedan återställa igen.</span><span class="sxs-lookup"><span data-stu-id="8c428-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="8c428-138">ELLER skriver du en ny primär e-postadress för användaren och väljer **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-138">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="8c428-139">Granska resultaten och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8c428-139">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="8c428-140">Återställa en användare som har en proxyadresskonflikt</span><span class="sxs-lookup"><span data-stu-id="8c428-140">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="8c428-p107">En proxyadresskonflikt inträffar när du tar bort ett användarkonto som innehåller en proxyadress, tilldelar ett annat konto samma proxyadress och sedan försöker återställa det borttagna kontot. Så här löser du problemet:</span><span class="sxs-lookup"><span data-stu-id="8c428-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="8c428-143">Du måste ha [administratörsbehörigheter](about-admin-roles.md) i Office 365 för att göra detta.</span><span class="sxs-lookup"><span data-stu-id="8c428-143">You must have [admin permissions](about-admin-roles.md) in Office 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8c428-144">Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8c428-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="8c428-145">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-145">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8c428-146">Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.</span><span class="sxs-lookup"><span data-stu-id="8c428-146">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="8c428-147">Markera användaren som ska återställas på sidan **Borttagna användare** och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-147">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="8c428-148">På sidan **Återställ** följer du instruktionerna för att ange lösenordet och väljer **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="8c428-148">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="8c428-149">Proxyadresser med konflikter tas automatiskt bort från användaren som du återställer.</span><span class="sxs-lookup"><span data-stu-id="8c428-149">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="8c428-150">Granska resultaten och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8c428-150">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8c428-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="8c428-151">Related articles</span></span>

[<span data-ttu-id="8c428-152">Ta bort en användare</span><span class="sxs-lookup"><span data-stu-id="8c428-152">Delete a user</span></span>](delete-a-user.md)
  

