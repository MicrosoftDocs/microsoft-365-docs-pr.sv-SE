---
title: Konvertera en användarpostlåda till en delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: 'Lär dig hur du konverterar en privat post låda till en delad post låda som kan användas av flera användare. '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445693"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="f3195-103">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="f3195-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="f3195-104">När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern.</span><span class="sxs-lookup"><span data-stu-id="f3195-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="f3195-105">Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person.</span><span class="sxs-lookup"><span data-stu-id="f3195-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="f3195-106">Vid ett senare datum kan du konvertera en delad post låda tillbaka till en användare (privat) post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="f3195-107">**Här är några viktiga saker som du måste känna till:**</span><span class="sxs-lookup"><span data-stu-id="f3195-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="f3195-108">Den användar post låda som du försöker att konvertera måste ha tilldelats en licens innan du konverterar den till en delad post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="f3195-109">Annars visas inte alternativet för att konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="f3195-110">Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="f3195-111">När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.</span><span class="sxs-lookup"><span data-stu-id="f3195-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="f3195-112">Delade post lådor kan ha upp till 50 GB data utan licens tilldelade till dem.</span><span class="sxs-lookup"><span data-stu-id="f3195-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="f3195-113">Om du vill ha mer information än den måste du ha en tilldelad licens.</span><span class="sxs-lookup"><span data-stu-id="f3195-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="f3195-114">Du kan behöva ta bort många e-postmeddelanden (till exempel till bilagor) från den delade post lådan för att krympa dem så att du kan ta bort licensen.</span><span class="sxs-lookup"><span data-stu-id="f3195-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="f3195-p104">Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="f3195-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="f3195-118">Reglerna är intakta efter att post lådan konverterats till en delad post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="f3195-119">Använda administrations centret för Exchange för att konvertera en post låda</span><span class="sxs-lookup"><span data-stu-id="f3195-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="f3195-120">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="f3195-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="f3195-121">Välj **mottagarnas** \> **post lådor**.</span><span class="sxs-lookup"><span data-stu-id="f3195-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="f3195-122">Välj användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-122">Select the user mailbox.</span></span> <span data-ttu-id="f3195-123">Välj **konvertera**under **konvertera till delad post låda**.</span><span class="sxs-lookup"><span data-stu-id="f3195-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f3195-124">Om post lådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="f3195-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="f3195-125">Ta inte bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="f3195-125">Don't delete the user's account.</span></span> <span data-ttu-id="f3195-126">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="f3195-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="f3195-127">Om du konverterar post lådan för en anställd som lämnar din organisation bör du vidta ytterligare åtgärder för att se till att de inte längre kan logga in.</span><span class="sxs-lookup"><span data-stu-id="f3195-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="f3195-128">Se [ta bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="f3195-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f3195-129">Det är inte nödvändigt att återställa användarens lösen ord under konvertering av post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="f3195-130">Men om lösen ordet inte återställs **fortsätter det ursprungliga användar namnet och lösen ordet efter att** post lådans konvertering är klar.</span><span class="sxs-lookup"><span data-stu-id="f3195-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="f3195-131">Om du behöver veta mer om delade post lådor läser du [om delade post lådor](about-shared-mailboxes.md) och [skapar en delad post låda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f3195-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f3195-132">Inga separata licenser krävs för delade post lådor.</span><span class="sxs-lookup"><span data-stu-id="f3195-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="f3195-133">Om du däremot vill aktivera In-Place arkiv eller skicka ett In-Place undantag eller en tvist i en delad post låda måste du tilldela en Exchange Online-prenumeration 1 med Exchange Online-arkivering eller Exchange Online abonnemang 2-licens till post lådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="f3195-134">Konvertera en borttagen användares postlåda</span><span class="sxs-lookup"><span data-stu-id="f3195-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="f3195-p109">Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:</span><span class="sxs-lookup"><span data-stu-id="f3195-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="f3195-137">[Återställ användarens konto](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="f3195-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="f3195-138">Kontrol lera att en Microsoft 365-licens har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="f3195-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="f3195-139">Återställ användarens lösen ord.</span><span class="sxs-lookup"><span data-stu-id="f3195-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="f3195-140">Vänta i 20-30 minuter på att postlådan återskapas.</span><span class="sxs-lookup"><span data-stu-id="f3195-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="f3195-141">Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="f3195-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="f3195-142">När det är klart kan du ta bort licensen från användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="f3195-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="f3195-143">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="f3195-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="f3195-144">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="f3195-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="f3195-145">Lägg till medlemmar för den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="f3195-146">Konvertera en delad post låda tillbaka till en användares (privat) post låda</span><span class="sxs-lookup"><span data-stu-id="f3195-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="f3195-147">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="f3195-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="f3195-148">Välj **Recipients** \> **delade**mottagare.</span><span class="sxs-lookup"><span data-stu-id="f3195-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="f3195-149">Välj den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-149">Select the shared mailbox.</span></span> <span data-ttu-id="f3195-150">Välj **konvertera**under **konvertera till vanlig post låda**.</span><span class="sxs-lookup"><span data-stu-id="f3195-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f3195-151">Gå tillbaka till administrations centret.</span><span class="sxs-lookup"><span data-stu-id="f3195-151">Go back to the admin center.</span></span> <span data-ttu-id="f3195-152">Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**.</span><span class="sxs-lookup"><span data-stu-id="f3195-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="f3195-153">Tilldela en licens till kontot och återställ lösenordet.</span><span class="sxs-lookup"><span data-stu-id="f3195-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="f3195-p113">Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="f3195-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="f3195-156">Konvertera en användares postlåda i en hybridmiljö</span><span class="sxs-lookup"><span data-stu-id="f3195-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="f3195-157">Om den delade post lådan är i en hybrid miljö **rekommenderar** vi att (nästan behöva!) du flyttar tillbaka användar post lådan till en delad post låda och sedan flyttar tillbaka den delade post lådan till molnet.</span><span class="sxs-lookup"><span data-stu-id="f3195-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="f3195-158">Så här gör du för att: om du konverterar post lådan i molnet kan den konverteras, men lokala användare tycker fortfarande att post lådan är post lådan, eftersom den nya verkligheten inte synkroniserar tillbaka till lokala platser.</span><span class="sxs-lookup"><span data-stu-id="f3195-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="f3195-159">Vanligt vis är det här inget problem, men det finns några scenarier där de lokala attributen (som tror att post lådan är användarens post låda) kan skriva över de nya moln versionerna av dessa attribut och det kan leda till att post lådan konverteras tillbaka.</span><span class="sxs-lookup"><span data-stu-id="f3195-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="f3195-160">Det här är ett problem med att användar post lådor kräver licenser **eller att de är mjuka borttagna efter 30 dagar**!</span><span class="sxs-lookup"><span data-stu-id="f3195-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="f3195-161">Vi har åtgärdat de flesta skälen till att det här gäller, men det kan ändå inträffa, trots att det inte är ofta.</span><span class="sxs-lookup"><span data-stu-id="f3195-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="f3195-162">Det bästa är att vara säkert och flytta tillbaka post lådan till lokal, konvertera den och sedan flytta tillbaka den delade post lådan till molnet.</span><span class="sxs-lookup"><span data-stu-id="f3195-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="f3195-163">Den rekommenderade lösningen är inte ett brott mot licens avtalet för Hybrid miljöer eftersom förekomsten av användar post lådan är bara tillfällig.</span><span class="sxs-lookup"><span data-stu-id="f3195-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="f3195-164">Du strider mot din licens om du bihörde användar post lådan eller den delade post lådan i din lokala organisation och inte flyttade den tillbaka till molnet.</span><span class="sxs-lookup"><span data-stu-id="f3195-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="f3195-165">Om du är medlem i roll gruppen organisations hantering eller mottagare kan du använda Exchange Management Shell för att ändra en användar post låda till en delad post låda lokalt.</span><span class="sxs-lookup"><span data-stu-id="f3195-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="f3195-166">Till exempel `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="f3195-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="f3195-167">Se lösningen i den här support lösningen för instanser när [delade post lådor oväntat omvandlas till användar post lådor](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="f3195-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f3195-168">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="f3195-168">Related articles</span></span>

[<span data-ttu-id="f3195-169">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="f3195-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f3195-170">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="f3195-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f3195-171">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="f3195-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f3195-172">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="f3195-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="f3195-173">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="f3195-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
