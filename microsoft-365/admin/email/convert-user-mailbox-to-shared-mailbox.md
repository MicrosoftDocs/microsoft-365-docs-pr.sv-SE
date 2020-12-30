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
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737971"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="9aa81-103">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="9aa81-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="9aa81-104">När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern.</span><span class="sxs-lookup"><span data-stu-id="9aa81-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="9aa81-105">Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person.</span><span class="sxs-lookup"><span data-stu-id="9aa81-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="9aa81-106">Vid ett senare datum kan du konvertera en delad post låda tillbaka till en användare (privat) post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="9aa81-107">**Här är några viktiga saker som du måste känna till:**</span><span class="sxs-lookup"><span data-stu-id="9aa81-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="9aa81-108">Den användar post låda som du försöker att konvertera måste ha tilldelats en licens innan du konverterar den till en delad post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="9aa81-109">Annars visas inte alternativet för att konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="9aa81-110">Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="9aa81-111">När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.</span><span class="sxs-lookup"><span data-stu-id="9aa81-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="9aa81-112">Delade post lådor kan ha upp till 50 GB data utan licens tilldelade till dem.</span><span class="sxs-lookup"><span data-stu-id="9aa81-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="9aa81-113">Om du vill ha mer information än den måste du ha en tilldelad licens.</span><span class="sxs-lookup"><span data-stu-id="9aa81-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="9aa81-114">Du kan behöva ta bort många e-postmeddelanden (till exempel till bilagor) från den delade post lådan för att krympa dem så att du kan ta bort licensen.</span><span class="sxs-lookup"><span data-stu-id="9aa81-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="9aa81-p104">Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="9aa81-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="9aa81-118">Reglerna är intakta efter att post lådan konverterats till en delad post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="9aa81-119">Använda administrations centret för Exchange för att konvertera en post låda</span><span class="sxs-lookup"><span data-stu-id="9aa81-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="9aa81-120">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="9aa81-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="9aa81-121">Välj **mottagarnas** \> **post lådor**.</span><span class="sxs-lookup"><span data-stu-id="9aa81-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="9aa81-122">Välj användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-122">Select the user mailbox.</span></span> <span data-ttu-id="9aa81-123">Välj **konvertera** under **konvertera till delad post låda**.</span><span class="sxs-lookup"><span data-stu-id="9aa81-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="9aa81-124">Om post lådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="9aa81-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="9aa81-125">Ta inte bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="9aa81-125">Don't delete the user's account.</span></span> <span data-ttu-id="9aa81-126">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="9aa81-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="9aa81-127">Om du konverterar post lådan för en anställd som lämnar din organisation bör du vidta ytterligare åtgärder för att se till att de inte längre kan logga in.</span><span class="sxs-lookup"><span data-stu-id="9aa81-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="9aa81-128">Se [ta bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="9aa81-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9aa81-129">Det är inte nödvändigt att återställa användarens lösen ord under konvertering av post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="9aa81-130">Men om lösen ordet inte återställs **fortsätter det ursprungliga användar namnet och lösen ordet efter att** post lådans konvertering är klar.</span><span class="sxs-lookup"><span data-stu-id="9aa81-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="9aa81-131">Om du behöver veta mer om delade post lådor läser du [om delade post lådor](about-shared-mailboxes.md) och [skapar en delad post låda](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="9aa81-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9aa81-132">Inga separata licenser krävs för delade post lådor.</span><span class="sxs-lookup"><span data-stu-id="9aa81-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="9aa81-133">Om du däremot vill aktivera In-Place arkiv eller skicka ett In-Place undantag eller en tvist i en delad post låda måste du tilldela en Exchange Online-prenumeration 1 med Exchange Online-arkivering eller Exchange Online abonnemang 2-licens till post lådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="9aa81-134">Konvertera en borttagen användares postlåda</span><span class="sxs-lookup"><span data-stu-id="9aa81-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="9aa81-p109">Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:</span><span class="sxs-lookup"><span data-stu-id="9aa81-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="9aa81-137">[Återställ användarens konto](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="9aa81-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="9aa81-138">Kontrol lera att en Microsoft 365-licens har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="9aa81-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="9aa81-139">Återställ användarens lösen ord.</span><span class="sxs-lookup"><span data-stu-id="9aa81-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="9aa81-140">Vänta i 20-30 minuter på att postlådan återskapas.</span><span class="sxs-lookup"><span data-stu-id="9aa81-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="9aa81-141">Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="9aa81-142">När det är klart kan du ta bort licensen från användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="9aa81-143">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="9aa81-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="9aa81-144">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="9aa81-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="9aa81-145">Lägg till medlemmar för den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="9aa81-146">Konvertera en delad post låda tillbaka till en användares (privat) post låda</span><span class="sxs-lookup"><span data-stu-id="9aa81-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="9aa81-147">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="9aa81-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="9aa81-148">Välj  \> **delade** mottagare.</span><span class="sxs-lookup"><span data-stu-id="9aa81-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="9aa81-149">Välj den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-149">Select the shared mailbox.</span></span> <span data-ttu-id="9aa81-150">Välj **konvertera** under **konvertera till vanlig post låda**.</span><span class="sxs-lookup"><span data-stu-id="9aa81-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="9aa81-151">Gå tillbaka till administrations centret.</span><span class="sxs-lookup"><span data-stu-id="9aa81-151">Go back to the admin center.</span></span> <span data-ttu-id="9aa81-152">Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**.</span><span class="sxs-lookup"><span data-stu-id="9aa81-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="9aa81-153">Tilldela en licens till kontot och återställ lösenordet.</span><span class="sxs-lookup"><span data-stu-id="9aa81-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="9aa81-p113">Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="9aa81-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="9aa81-156">Konvertera en användares postlåda i en hybridmiljö</span><span class="sxs-lookup"><span data-stu-id="9aa81-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="9aa81-157">Mer information om hur du konverterar en användar post låda till en delad post låda i en Exchange-hybrid miljö finns i:</span><span class="sxs-lookup"><span data-stu-id="9aa81-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="9aa81-158">Cmdlets för att skapa eller ändra en delad fjärrpostlåda i en lokal Exchange-miljö</span><span class="sxs-lookup"><span data-stu-id="9aa81-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="9aa81-159">Delade post lådor konverteras oväntat till användar post lådor efter att profilsynkronisering körs i en Exchange hybrid distribution</span><span class="sxs-lookup"><span data-stu-id="9aa81-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="9aa81-160">Om du är medlem i roll gruppen organisations hantering eller mottagare kan du använda Exchange Management Shell för att ändra en användar post låda till en delad post låda lokalt.</span><span class="sxs-lookup"><span data-stu-id="9aa81-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="9aa81-161">Till exempel `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="9aa81-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9aa81-162">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9aa81-162">Related articles</span></span>

[<span data-ttu-id="9aa81-163">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="9aa81-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="9aa81-164">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="9aa81-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="9aa81-165">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="9aa81-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="9aa81-166">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="9aa81-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="9aa81-167">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="9aa81-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
