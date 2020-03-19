---
title: Konvertera en användarpostlåda till en delad postlåda
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Lär dig att konvertera en privat postlåda till en delad postlåda som kan nås av flera användare. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811957"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="ea659-103">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="ea659-104">När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern.</span><span class="sxs-lookup"><span data-stu-id="ea659-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="ea659-105">Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person.</span><span class="sxs-lookup"><span data-stu-id="ea659-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="ea659-106">Vid ett senare tillfälle kan du konvertera en delad postlåda tillbaka till en användare (privat) postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="ea659-107">**Här är några riktigt viktiga saker som du behöver veta:**</span><span class="sxs-lookup"><span data-stu-id="ea659-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="ea659-108">Användarpostlådan som du konverterar behöver en licens som tilldelats den innan du konverterar den till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="ea659-109">Annars visas inte alternativet för att konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="ea659-110">Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="ea659-111">När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.</span><span class="sxs-lookup"><span data-stu-id="ea659-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="ea659-p103">Delade postlådor kan ha upp till 50 GB data utan att någon tilldelad licens. Om postlådan ska innehålla mer data än det behöver du tilldela en licens till den. Du kanske måste ta bort flera stora e-postmeddelanden (t.ex. sådana med bifogade filer) från den delade postlådan för att krympa dess storlek så att du kan ta bort licensen.</span><span class="sxs-lookup"><span data-stu-id="ea659-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="ea659-p104">Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="ea659-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="ea659-118">Reglerna är intakta när postlådan har konverterats till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="ea659-119">Använda administrationscentret för Exchange för att konvertera en postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="ea659-120">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ea659-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="ea659-121">Välj **mottagare postlådor** \> **Mailboxes**.</span><span class="sxs-lookup"><span data-stu-id="ea659-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="ea659-122">Markera användarpostlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-122">Select the user mailbox.</span></span> <span data-ttu-id="ea659-123">Välj **Konvertera**under **Konvertera till delad postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ea659-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ea659-124">Om postlådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md) och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="ea659-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="ea659-125">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="ea659-126">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="ea659-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="ea659-127">Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre.</span><span class="sxs-lookup"><span data-stu-id="ea659-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="ea659-128">Se [Ta bort en tidigare anställd från Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="ea659-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="ea659-129">För allt annat du behöver veta om delade postlådor, se [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ea659-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="ea659-130">Använda administrationscentret för Microsoft 365 för att konvertera en postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ea659-131">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ea659-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ea659-132">Välj namnet på den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="ea659-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="ea659-133">Återställ användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="ea659-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="ea659-134">Det krävs inte för att återställa användarens lösenord under postlådekonverteringen.</span><span class="sxs-lookup"><span data-stu-id="ea659-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="ea659-135">Men om lösenordet inte återställs **fortsätter det ursprungliga användarnamnet och lösenordet att fungera** när postlådans konvertering är klar.</span><span class="sxs-lookup"><span data-stu-id="ea659-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="ea659-136">Välj Konvertera till delad postlåda under **Fler åtgärder**på fliken **E-post.** **Convert to shared mailbox**</span><span class="sxs-lookup"><span data-stu-id="ea659-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ea659-137">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ea659-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ea659-138">Markera den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="ea659-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="ea659-139">Expandera **E-postinställningar**i den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="ea659-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="ea659-140">Bredvid **Fler inställningar**väljer du Konvertera till delad **postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ea659-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ea659-141">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ea659-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ea659-142">Markera den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="ea659-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="ea659-143">Expandera **E-postinställningar**i den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="ea659-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="ea659-144">Bredvid **Fler inställningar**väljer du Konvertera till delad **postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ea659-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="ea659-145">Om postlådan är mindre än 50 GB kan du [ta bort licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="ea659-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="ea659-146">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="ea659-147">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="ea659-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="ea659-148">Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre.</span><span class="sxs-lookup"><span data-stu-id="ea659-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="ea659-149">Se [Ta bort en tidigare anställd från Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="ea659-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="ea659-150">För allt annat du behöver veta om delade postlådor, se [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ea659-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="ea659-151">Konvertera en borttagen användares postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="ea659-p111">Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:</span><span class="sxs-lookup"><span data-stu-id="ea659-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="ea659-154">[Återställ användarens konto](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="ea659-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="ea659-155">Kontrollera att en Office 365-licens har tilldelats till det.</span><span class="sxs-lookup"><span data-stu-id="ea659-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="ea659-156">Återställ användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="ea659-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="ea659-157">Vänta i 20-30 minuter på att postlådan återskapas.</span><span class="sxs-lookup"><span data-stu-id="ea659-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="ea659-158">Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="ea659-159">När det är gjort kan du ta bort licensen från användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="ea659-160">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="ea659-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="ea659-161">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="ea659-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="ea659-162">Lägg till medlemmar för den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="ea659-163">Konvertera en delad postlåda tillbaka till en användares (privata) postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="ea659-164">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ea659-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="ea659-165">Välj **Delade mottagare** \> **.**</span><span class="sxs-lookup"><span data-stu-id="ea659-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="ea659-166">Markera den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-166">Select the shared mailbox.</span></span> <span data-ttu-id="ea659-167">Välj **Konvertera**under **Konvertera till vanlig postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ea659-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ea659-168">Gå tillbaka till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="ea659-168">Go back to the admin center.</span></span> <span data-ttu-id="ea659-169">Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**.</span><span class="sxs-lookup"><span data-stu-id="ea659-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="ea659-170">Tilldela en licens till kontot och återställ lösenordet.</span><span class="sxs-lookup"><span data-stu-id="ea659-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="ea659-p115">Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ea659-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="ea659-173">Konvertera en användares postlåda i en hybridmiljö</span><span class="sxs-lookup"><span data-stu-id="ea659-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="ea659-174">Om den här delade postlådan är i en hybridmiljö rekommenderar vi **starkt** (nästan kräver!) att du flyttar tillbaka användarpostlådan till lokal, konverterar användarpostlådan till en delad postlåda och flyttar sedan den delade postlådan tillbaka till molnet.</span><span class="sxs-lookup"><span data-stu-id="ea659-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="ea659-175">Här är varför: om du konverterar postlådan i molnet kan den konverteras, men lokalt tror fortfarande att postlådan är användarpostlådan, eftersom den nya verkligheten inte synkroniseras tillbaka till lokala.</span><span class="sxs-lookup"><span data-stu-id="ea659-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="ea659-176">Vanligtvis är detta inte ett problem, men det finns vissa scenarier där de lokala attributen (som tror att postlådan är användarenpostlådan) kan skriva över de nya molnversionerna av dessa attribut, och som ett resultat kan postlådan konvertera tillbaka.</span><span class="sxs-lookup"><span data-stu-id="ea659-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="ea659-177">Detta är ett problem eftersom användarpostlådor kräver licenser **eller de är mjuka bort efter 30 dagar!**</span><span class="sxs-lookup"><span data-stu-id="ea659-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="ea659-178">Vi har tagit upp de flesta av anledningarna till att detta händer men det kan fortfarande hända, men sällan.</span><span class="sxs-lookup"><span data-stu-id="ea659-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="ea659-179">Det är bäst att vara säker och flytta brevlådan tillbaka till lokala.</span><span class="sxs-lookup"><span data-stu-id="ea659-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="ea659-180">Om du är en del av organisationshantering eller mottagarhantering kan du använda skalet för Exchange Management för att ändra en användarpostlåda till en delad postlåda lokalt.</span><span class="sxs-lookup"><span data-stu-id="ea659-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="ea659-181">Till exempel `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="ea659-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="ea659-182">Se lösningen i den här supportlösningen till exempel när [delade postlådor oväntat konverteras till användarpostlådor](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="ea659-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="ea659-183">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ea659-183">Related articles</span></span>

[<span data-ttu-id="ea659-184">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ea659-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ea659-185">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="ea659-186">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="ea659-187">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ea659-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="ea659-188">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ea659-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
