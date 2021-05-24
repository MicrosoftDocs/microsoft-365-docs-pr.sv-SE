---
title: Återställa en användare
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Inom 30 dagar efter att du tagit bort ett användarkonto kan du återställa kontot och alla data och användaren kan logga in med samma konto.
ms.openlocfilehash: 83852136ee22ab3f63d8ada6a5a7290883c392e5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623827"
---
# <a name="restore-a-user"></a><span data-ttu-id="d33f9-103">Återställa en användare</span><span class="sxs-lookup"><span data-stu-id="d33f9-103">Restore a user</span></span>
   
<span data-ttu-id="d33f9-p101">Om du återställer ett användarkonto inom 30 dagar från det att det togs bort, återställs kontot och alla associerade data. Användaren kan logga in med samma arbets- eller skolkonto. Postlådan återställs i sin helhet. Om du vill ta reda på hur mycket tid som återstår innan ett visst användarkonto inte längre kan återställas [kontaktar du oss](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="d33f9-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="d33f9-108">Här är några tips:</span><span class="sxs-lookup"><span data-stu-id="d33f9-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="d33f9-109">Se till att det finns tillgängliga licenser att tilldela kontot.</span><span class="sxs-lookup"><span data-stu-id="d33f9-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="d33f9-110">Om ditt företag använder Active Directory, se [Felsökning av borttagna konton i Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) för instruktioner om återställning av användarkonton.</span><span class="sxs-lookup"><span data-stu-id="d33f9-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="d33f9-111">Återställa ett eller flera användarkonton</span><span class="sxs-lookup"><span data-stu-id="d33f9-111">Restore one or more user accounts</span></span>

<span data-ttu-id="d33f9-112">Du måste vara global Microsoft 365 administratör eller användarhanteringsadministratör för att kunna göra det här.</span><span class="sxs-lookup"><span data-stu-id="d33f9-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="d33f9-113">I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.</span><span class="sxs-lookup"><span data-stu-id="d33f9-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="d33f9-114">På sidan **Borttagna användare** markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="d33f9-115">Följ anvisningarna för att ange deras lösenord och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="d33f9-116">Om användaren återställs väljer du Skicka **e-post och stäng**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="d33f9-117">Om det uppstår en namnkonflikt eller en proxyadresskonflikt kan du läsa instruktionerna nedan om återställning av dessa konton.</span><span class="sxs-lookup"><span data-stu-id="d33f9-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="d33f9-118">När du har återställt en användare bör du meddela dem att deras lösenord har ändrats och följa upp med dem.</span><span class="sxs-lookup"><span data-stu-id="d33f9-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="d33f9-119">Återställa en användare som har en användarnamnskonflikt</span><span class="sxs-lookup"><span data-stu-id="d33f9-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="d33f9-120">En användarnamnskonflikt inträffar när du tar bort ett användarkonto, skapar ett nytt användarkonto med samma användarnamn (antingen för samma användare eller för en annan användare med ett liknande namn) och sedan försöker återställa det borttagna kontot.</span><span class="sxs-lookup"><span data-stu-id="d33f9-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="d33f9-p103">Om du vill lösa detta ersätter du det aktiva användarkontot med det konto som du återställer. Eller tilldela det konto som du återställer ett annat användarnamn, så att inte båda kontona har samma användarnamn. Följ nedanstående anvisningar.</span><span class="sxs-lookup"><span data-stu-id="d33f9-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="d33f9-124">I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.</span><span class="sxs-lookup"><span data-stu-id="d33f9-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="d33f9-125">På **sidan Borttagna** användare markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d33f9-p104">Om återställandet av två eller fler användare misslyckas visas ett felmeddelande som informerar dig om att återställningsåtgärden misslyckades för vissa användare. Ta fram loggen och kontrollera vilka användare som inte återställdes. Dessa konton måste du återställa ett åt gången.</span><span class="sxs-lookup"><span data-stu-id="d33f9-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="d33f9-128">Följ anvisningarna för att ange lösenordet och välj **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="d33f9-p105">Ett meddelande dyker upp där det står att det inte gick att återställa kontot. Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="d33f9-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="d33f9-p106">Avbryt återställningen och byt namn på den aktiva användaren. Försök sedan återställa igen.</span><span class="sxs-lookup"><span data-stu-id="d33f9-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="d33f9-133">ELLER, skriv en ny primär e-postadress för användaren och välj **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="d33f9-134">Granska resultaten och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="d33f9-135">Återställa en användare som har en proxyadresskonflikt</span><span class="sxs-lookup"><span data-stu-id="d33f9-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="d33f9-p107">En proxyadresskonflikt inträffar när du tar bort ett användarkonto som innehåller en proxyadress, tilldelar ett annat konto samma proxyadress och sedan försöker återställa det borttagna kontot. Så här löser du problemet:</span><span class="sxs-lookup"><span data-stu-id="d33f9-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="d33f9-138">Du måste ha [administratörsbehörighet](about-admin-roles.md) i Microsoft 365 göra detta.</span><span class="sxs-lookup"><span data-stu-id="d33f9-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="d33f9-139">I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.</span><span class="sxs-lookup"><span data-stu-id="d33f9-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="d33f9-140">Markera användaren som ska återställas på sidan **Borttagna användare** och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="d33f9-141">På sidan **Återställ** följer du anvisningarna för att ange lösenordet och väljer **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="d33f9-142">Proxyadresser med konflikter tas automatiskt bort från användaren som du återställer.</span><span class="sxs-lookup"><span data-stu-id="d33f9-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="d33f9-143">Granska resultaten och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d33f9-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="d33f9-144">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="d33f9-144">Related content</span></span>

<span data-ttu-id="d33f9-145">[Ta bort en användare](delete-a-user.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d33f9-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="d33f9-146">[Tilldela administratörsroller](assign-admin-roles.md) (video)</span><span class="sxs-lookup"><span data-stu-id="d33f9-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="d33f9-147">[Tilldela användare licenser](../manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d33f9-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
