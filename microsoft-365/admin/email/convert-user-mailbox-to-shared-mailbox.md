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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Lär dig att konvertera en privat postlåda till en delad postlåda som kan nås av flera användare. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521035"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="333af-103">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="333af-104">När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern.</span><span class="sxs-lookup"><span data-stu-id="333af-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="333af-105">Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person.</span><span class="sxs-lookup"><span data-stu-id="333af-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="333af-106">Vid ett senare tillfälle kan du konvertera tillbaka en delad postlåda till en användare (privat) postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="333af-107">**Här är några riktigt viktiga saker som du behöver veta:**</span><span class="sxs-lookup"><span data-stu-id="333af-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="333af-108">Användarpostlådan som du konverterar behöver en licens som tilldelats den innan du konverterar den till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="333af-109">Annars visas inte alternativet för att konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="333af-110">Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="333af-111">När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.</span><span class="sxs-lookup"><span data-stu-id="333af-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="333af-112">Delade postlådor kan ha upp till 50 GB data utan att en licens har tilldelats dem.</span><span class="sxs-lookup"><span data-stu-id="333af-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="333af-113">Om du vill behålla mer data än så behöver du en licens som tilldelats den.</span><span class="sxs-lookup"><span data-stu-id="333af-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="333af-114">Du kan behöva ta bort en massa stora e-postmeddelanden (säg, de med bilagor) från den delade postlådan för att krympa den så att du kan ta bort licensen.</span><span class="sxs-lookup"><span data-stu-id="333af-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="333af-p104">Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="333af-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="333af-118">Reglerna är intakta när postlådan har konverterats till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="333af-119">Använda administrationscentret för Exchange för att konvertera en postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="333af-120">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="333af-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="333af-121">Välj **Mottagare** \> **Postlådor**.</span><span class="sxs-lookup"><span data-stu-id="333af-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="333af-122">Markera användarpostlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-122">Select the user mailbox.</span></span> <span data-ttu-id="333af-123">Under **Konvertera till delad postlåda**väljer du **Konvertera**.</span><span class="sxs-lookup"><span data-stu-id="333af-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="333af-124">Om postlådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="333af-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="333af-125">Ta inte bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="333af-125">Don't delete the user's account.</span></span> <span data-ttu-id="333af-126">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="333af-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="333af-127">Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre.</span><span class="sxs-lookup"><span data-stu-id="333af-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="333af-128">Se [Ta bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="333af-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="333af-129">Allt annat du behöver veta om delade postlådor finns i [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="333af-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="333af-130">Använda administrationscentret för Microsoft 365 för att konvertera en postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="333af-131">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="333af-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="333af-132">Markera namnet på den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="333af-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="333af-133">Återställ användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="333af-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="333af-134">Det krävs inte att återställa användarens lösenord under postlådekonvertering.</span><span class="sxs-lookup"><span data-stu-id="333af-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="333af-135">Men om lösenordet inte återställs **fortsätter det ursprungliga användarnamnet och lösenordet att fungera** när postlådekonverteringen är klar.</span><span class="sxs-lookup"><span data-stu-id="333af-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="333af-136">Välj **Konvertera till delad postlåda**under Fler **åtgärder**på fliken **E-post** .</span><span class="sxs-lookup"><span data-stu-id="333af-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="333af-137">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="333af-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="333af-138">Markera den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="333af-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="333af-139">Expandera **E-postinställningar i**den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="333af-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="333af-140">Välj Konvertera till **delad postlåda**bredvid **Fler inställningar**.</span><span class="sxs-lookup"><span data-stu-id="333af-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="333af-141">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="333af-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="333af-142">Markera den användare vars postlåda du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="333af-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="333af-143">Expandera **E-postinställningar i**den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="333af-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="333af-144">Välj Konvertera till **delad postlåda**bredvid **Fler inställningar**.</span><span class="sxs-lookup"><span data-stu-id="333af-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="333af-145">Om postlådan är mindre än 50 GB kan du [ta bort licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="333af-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="333af-146">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="333af-147">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="333af-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="333af-148">Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre.</span><span class="sxs-lookup"><span data-stu-id="333af-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="333af-149">Se [Ta bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="333af-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="333af-150">Allt annat du behöver veta om delade postlådor finns i [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="333af-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="333af-151">Delade postlådor kräver ingen separat licens.</span><span class="sxs-lookup"><span data-stu-id="333af-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="333af-152">Om du vill aktivera Arkiv på plats eller placera ett spärrat på plats eller spärra av juridiska skäl på en delad postlåda måste du dock tilldela en Exchange Online-plan 1 med Exchange Online Archiving- eller Exchange Online Plan 2-licens till postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="333af-153">Konvertera en borttagen användares postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="333af-p112">Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:</span><span class="sxs-lookup"><span data-stu-id="333af-p112">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="333af-156">[Återställ användarens konto](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="333af-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="333af-157">Kontrollera att en Microsoft 365-licens har tilldelats den.</span><span class="sxs-lookup"><span data-stu-id="333af-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="333af-158">Återställ användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="333af-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="333af-159">Vänta i 20-30 minuter på att postlådan återskapas.</span><span class="sxs-lookup"><span data-stu-id="333af-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="333af-160">Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="333af-161">När det är klart kan du ta bort licensen från användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="333af-162">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="333af-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="333af-163">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="333af-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="333af-164">Lägg till medlemmar för den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="333af-165">Konvertera en delad postlåda tillbaka till en användares (privata) postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="333af-166">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="333af-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="333af-167">Välj **Delade mottagare** \> **Shared**.</span><span class="sxs-lookup"><span data-stu-id="333af-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="333af-168">Markera den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-168">Select the shared mailbox.</span></span> <span data-ttu-id="333af-169">Under **Konvertera till vanlig postlåda**väljer du **Konvertera**.</span><span class="sxs-lookup"><span data-stu-id="333af-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="333af-170">Gå tillbaka till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="333af-170">Go back to the admin center.</span></span> <span data-ttu-id="333af-171">Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**.</span><span class="sxs-lookup"><span data-stu-id="333af-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="333af-172">Tilldela en licens till kontot och återställ lösenordet.</span><span class="sxs-lookup"><span data-stu-id="333af-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="333af-p116">Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="333af-p116">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="333af-175">Konvertera en användares postlåda i en hybridmiljö</span><span class="sxs-lookup"><span data-stu-id="333af-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="333af-176">Om den här delade postlådan finns i en hybridmiljö rekommenderar vi **starkt** (nästan behöver!) att du flyttar tillbaka användarpostlådan till lokalt, konverterar användarpostlådan till en delad postlåda och sedan flyttar tillbaka den delade postlådan till molnet.</span><span class="sxs-lookup"><span data-stu-id="333af-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="333af-177">Här är anledningen: om du konverterar postlådan i molnet kan den konverteras, men lokalt fortfarande tror att postlådan är användarpostlådan, eftersom den nya verkligheten inte synkroniseras tillbaka till lokalt.</span><span class="sxs-lookup"><span data-stu-id="333af-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="333af-178">Vanligtvis är detta inte ett problem, men det finns vissa scenarier där lokala attribut (som tror att postlådan är användarpostlådan) kan skriva över de nya molnversionerna av dessa attribut, och som ett resultat kan postlådan konverteras tillbaka.</span><span class="sxs-lookup"><span data-stu-id="333af-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="333af-179">Detta är ett problem eftersom användaren brevlådor kräver licenser **eller de är mjuka bort efter 30 dagar!**</span><span class="sxs-lookup"><span data-stu-id="333af-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="333af-180">Vi har tagit upp de flesta av anledningarna till att detta händer men det kan fortfarande hända, men sällan.</span><span class="sxs-lookup"><span data-stu-id="333af-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="333af-181">Det är bäst att vara säker och flytta tillbaka postlådan till lokalt, konvertera den och sedan flytta tillbaka den delade postlådan till molnet.</span><span class="sxs-lookup"><span data-stu-id="333af-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="333af-182">Den här rekommenderade lösningen bryter inte mot licensavtalet för hybridmiljöer eftersom förekomsten av användarpostlådan lokalt bara är tillfällig.</span><span class="sxs-lookup"><span data-stu-id="333af-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="333af-183">Du skulle bryta mot din licens om du underhållit användarpostlådan eller den delade postlådan i din lokala organisation och inte flyttade tillbaka den till molnet.</span><span class="sxs-lookup"><span data-stu-id="333af-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="333af-184">Om du är medlem i rollgruppen Organisationshantering eller Mottagarhantering kan du använda exchange management-gränssnittet för att ändra en användarpostlåda till en delad postlåda lokalt.</span><span class="sxs-lookup"><span data-stu-id="333af-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="333af-185">Till exempel `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="333af-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="333af-186">Se lösningen i den här supportlösningen för instanser när [delade postlådor oväntat konverteras till användarpostlådor](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="333af-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="333af-187">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="333af-187">Related articles</span></span>

[<span data-ttu-id="333af-188">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="333af-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="333af-189">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="333af-190">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="333af-191">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="333af-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="333af-192">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="333af-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
