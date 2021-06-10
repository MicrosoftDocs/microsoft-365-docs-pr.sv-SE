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
description: 'Lär dig hur du konverterar en privat postlåda till en delad postlåda som flera personer kan komma åt istället för bara en person. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635480"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="56f06-103">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="56f06-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="56f06-104">När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern.</span><span class="sxs-lookup"><span data-stu-id="56f06-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="56f06-105">Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person.</span><span class="sxs-lookup"><span data-stu-id="56f06-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="56f06-106">Du kan senare konvertera en delad postlåda tillbaka till en användarpostlåda (privat).</span><span class="sxs-lookup"><span data-stu-id="56f06-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="56f06-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="56f06-107">Before you begin</span></span>

<span data-ttu-id="56f06-108">**Här är några mycket viktiga saker som du behöver veta:**</span><span class="sxs-lookup"><span data-stu-id="56f06-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="56f06-109">Den användarpostlåda du konverterar måste ha en tilldelad licens innan du konverterar postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="56f06-110">Annars visas inte alternativet för att konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="56f06-111">Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="56f06-112">När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.</span><span class="sxs-lookup"><span data-stu-id="56f06-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="56f06-113">Delade postlådor kan ha upp till 50 GB data utan att någon tilldelad licens.</span><span class="sxs-lookup"><span data-stu-id="56f06-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="56f06-114">Om du vill lagra mer data än det behöver du tilldela en licens till den.</span><span class="sxs-lookup"><span data-stu-id="56f06-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="56f06-115">Du kan behöva ta bort flera stora e-postmeddelanden (t.ex. sådana med bifogade filer) från den delade postlådan för att krympa den så att du kan ta bort licensen.</span><span class="sxs-lookup"><span data-stu-id="56f06-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="56f06-p104">Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="56f06-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="56f06-119">Reglerna är intakta när postlådan har konverterats till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="56f06-120">Använda administrationscentret Exchange för att konvertera en postlåda</span><span class="sxs-lookup"><span data-stu-id="56f06-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="56f06-121">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="56f06-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="56f06-122">Välj  \> **Mottagare, postlådor**.</span><span class="sxs-lookup"><span data-stu-id="56f06-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="56f06-123">Markera användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-123">Select the user mailbox.</span></span> <span data-ttu-id="56f06-124">Under **Konvertera till delad postlåda** väljer du **Konvertera**.</span><span class="sxs-lookup"><span data-stu-id="56f06-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="56f06-125">Om postlådan är mindre än 50 GB kan du ta bort licensen från [användaren](../manage/remove-licenses-from-users.md)och sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="56f06-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="56f06-126">Ta inte bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="56f06-126">Don't delete the user's account.</span></span> <span data-ttu-id="56f06-127">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="56f06-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="56f06-128">Om du konverterar postlådan för en anställd som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre.</span><span class="sxs-lookup"><span data-stu-id="56f06-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="56f06-129">Se Ta [bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="56f06-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="56f06-130">Det är inte obligatoriskt att återställa användarens lösenord vid postlådekonvertering.</span><span class="sxs-lookup"><span data-stu-id="56f06-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="56f06-131">Om lösenordet inte återställs fortsätter det ursprungliga **användarnamnet och lösenordet att fungera** när postlådekonverteringen är klar.</span><span class="sxs-lookup"><span data-stu-id="56f06-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="56f06-132">Allt annat du behöver veta om delade postlådor finns i [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="56f06-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="56f06-133">Delade postlådor kräver inte en separat licens.</span><span class="sxs-lookup"><span data-stu-id="56f06-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="56f06-134">Om du däremot vill aktivera In-Place-arkiv eller placera en licens för In-Place-bevarande eller bevarande av juridiska skäl för en delad postlåda måste du tilldela en licens för Exchange Online-abonnemang 1 med Exchange Online - arkivering eller Exchange Online abonnemang 2 till postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="56f06-135">Konvertera en borttagen användares postlåda</span><span class="sxs-lookup"><span data-stu-id="56f06-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="56f06-p109">Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:</span><span class="sxs-lookup"><span data-stu-id="56f06-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="56f06-138">[Återställa användarens konto.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="56f06-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="56f06-139">Kontrollera att Microsoft 365 licens är tilldelad till den.</span><span class="sxs-lookup"><span data-stu-id="56f06-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="56f06-140">Återställ användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="56f06-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="56f06-141">Vänta i 20-30 minuter på att postlådan återskapas.</span><span class="sxs-lookup"><span data-stu-id="56f06-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="56f06-142">Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="56f06-143">När det är klart kan du ta bort licensen från användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="56f06-144">Ta inte bort användarens gamla postlåda.</span><span class="sxs-lookup"><span data-stu-id="56f06-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="56f06-145">Den delade postlådan behöver ha den som en fästpunkt.</span><span class="sxs-lookup"><span data-stu-id="56f06-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="56f06-146">Lägg till medlemmar för den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="56f06-147">Konvertera en delad postlåda tillbaka till en användares (privata) postlåda</span><span class="sxs-lookup"><span data-stu-id="56f06-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="56f06-148">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="56f06-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="56f06-149">Välj **Mottagare som** \> **delas**.</span><span class="sxs-lookup"><span data-stu-id="56f06-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="56f06-150">Välj den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-150">Select the shared mailbox.</span></span> <span data-ttu-id="56f06-151">Under **Konvertera till vanlig postlåda** väljer du **Konvertera**.</span><span class="sxs-lookup"><span data-stu-id="56f06-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="56f06-152">Gå tillbaka till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="56f06-152">Go back to the admin center.</span></span> <span data-ttu-id="56f06-153">Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**.</span><span class="sxs-lookup"><span data-stu-id="56f06-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="56f06-154">Tilldela en licens till kontot och återställ lösenordet.</span><span class="sxs-lookup"><span data-stu-id="56f06-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="56f06-p113">Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="56f06-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="56f06-157">Konvertera en användares postlåda i en hybridmiljö</span><span class="sxs-lookup"><span data-stu-id="56f06-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="56f06-158">Mer information om hur du konverterar en användarpostlåda till en delad postlåda i Exchange hybridmiljö finns i:</span><span class="sxs-lookup"><span data-stu-id="56f06-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="56f06-159">Cmdlets för att skapa eller ändra en fjärransluten delad postlåda i en Exchange miljö</span><span class="sxs-lookup"><span data-stu-id="56f06-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="56f06-160">Delade postlådor konverteras oväntat till användarpostlådor när katalogsynkroniseringen har Exchange i en hybriddistribution</span><span class="sxs-lookup"><span data-stu-id="56f06-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="56f06-161">Om du är medlem i rollgruppen Organisationshantering eller Mottagarhantering kan du använda Exchange Management Shell för att ändra en användarpostlåda till en delad postlåda lokalt.</span><span class="sxs-lookup"><span data-stu-id="56f06-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="56f06-162">Till exempel `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="56f06-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="56f06-163">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="56f06-163">Related content</span></span>

<span data-ttu-id="56f06-164">[Om delade postlådor](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="56f06-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="56f06-165">[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="56f06-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="56f06-166">[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="56f06-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="56f06-167">[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="56f06-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="56f06-168">[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="56f06-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>