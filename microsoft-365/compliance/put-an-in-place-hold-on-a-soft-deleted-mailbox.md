---
title: Placera en In-Place på en mjukt borttagna postlåda i Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skapar ett In-Place för en mjukt borttagna postlåda så att den blir inaktiv och bevarar innehållet.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226101"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="a6441-103">Placera en In-Place på en mjukt borttagna postlåda i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a6441-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="a6441-104">Lär dig hur du skapar ett In-Place för en mjukt borttagna postlåda så att den blir inaktiv och bevarar innehållet.</span><span class="sxs-lookup"><span data-stu-id="a6441-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="a6441-105">Sedan kan du använda Microsoft-verktyg för eDiscovery för att söka i den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="a6441-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6441-106">Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet tillkännager vi att In-Place Holds i administrationscentret för Exchange (EAC) kommer att gå ur.</span><span class="sxs-lookup"><span data-stu-id="a6441-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="a6441-107">Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a6441-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="a6441-108">Men du kan fortfarande hantera e-In-Place i EAC eller med hjälp av **cmdleten Set-MailboxSearch** i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6441-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="a6441-109">Men med början den 1 oktober 2020 kan du inte hantera nya In-Place.</span><span class="sxs-lookup"><span data-stu-id="a6441-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="a6441-110">Du tar bara bort dem i EAC eller med cmdleten **Remove-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="a6441-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="a6441-111">Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="a6441-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

<span data-ttu-id="a6441-112">Du kanske har en situation där en person har lämnat organisationen och deras motsvarande användarkonto och postlåda har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="a6441-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="a6441-113">Därefter inser du att det finns information i postlådan som måste bevaras.</span><span class="sxs-lookup"><span data-stu-id="a6441-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="a6441-114">Vad kan du göra?</span><span class="sxs-lookup"><span data-stu-id="a6441-114">What can you do?</span></span> <span data-ttu-id="a6441-115">Om den borttagna postlådans bevarandeperiod inte har förfallit kan du placera en In-Place på den borttagna postlådan (en så kallad mjuk borttagna postlåda) och göra den till en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="a6441-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a soft-deleted mailbox) and make it an inactive mailbox.</span></span> <span data-ttu-id="a6441-116">En  *inaktiv postlåda*  används för att bevara en tidigare anställds e-post när han eller hon lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="a6441-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="a6441-117">Innehållet i en inaktiv postlåda bevaras under tiden den inaktiva In-Place som placerades på den mjukt borttagna postlådan när den gjordes inaktiv.</span><span class="sxs-lookup"><span data-stu-id="a6441-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="a6441-118">När postlådan har gjorts inaktiv kan du söka i postlådan med hjälp av In-Place eDiscovery i Exchange Online, innehållssökning i säkerhets- & och efterlevnadscentret eller eDiscovery Center i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a6441-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span>

> [!NOTE]
> <span data-ttu-id="a6441-119">I Exchange Online är en mjuk borttagna postlåda en postlåda som har tagits bort men kan återställas inom en viss bevarandeperiod.</span><span class="sxs-lookup"><span data-stu-id="a6441-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="a6441-120">Bevarandetiden för den mjukt borttagna postlådan i Exchange Online är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="a6441-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="a6441-121">Det innebär att postlådan kan återställas (eller göras till en inaktiv postlåda) inom 30 dagar efter att den togs bort.</span><span class="sxs-lookup"><span data-stu-id="a6441-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="a6441-122">Efter 30 dagar markeras en mjuk borttagen postlåda för permanent borttagning och kan inte återställas eller göras inaktiv.</span><span class="sxs-lookup"><span data-stu-id="a6441-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span>

## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="a6441-123">Krav för In-Place rymmer</span><span class="sxs-lookup"><span data-stu-id="a6441-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="a6441-124">Du måste använda cmdleten **New-MailboxSearch** i Windows PowerShell placera en In-Place på en mjuk borttagna postlåda.</span><span class="sxs-lookup"><span data-stu-id="a6441-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="a6441-125">Du kan inte använda administrationscentret Exchange (EAC) eller eDiscovery Center i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a6441-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span>

- <span data-ttu-id="a6441-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a6441-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a6441-127">Kör följande kommando för att få identitetsinformation om mjukt borttagna postlådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a6441-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="a6441-128">Mer information om inaktiva postlådor finns i [Översikt över inaktiva postlådor i Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a6441-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="a6441-129">Placera en In-Place på en mjuk borttagna postlåda för att göra den till en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="a6441-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="a6441-130">Använd **cmdleten New-MailboxSearch** till att göra en mjuk borttagna postlåda till en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="a6441-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="a6441-131">Mer information finns i [Ny postlådesökning](/powershell/module/exchange/new-mailboxsearch).</span><span class="sxs-lookup"><span data-stu-id="a6441-131">For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>

1. <span data-ttu-id="a6441-132">Skapa en variabel som innehåller egenskaperna för den mjukt borttagna postlådan.</span><span class="sxs-lookup"><span data-stu-id="a6441-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="a6441-133">I det föregående kommandot använder du värdet för egenskapen **DistinguishedName** eller **ExchangeGuid** för att identifiera den mjukt borttagna postlådan.</span><span class="sxs-lookup"><span data-stu-id="a6441-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="a6441-134">De här egenskaperna är unika för varje postlåda i organisationen, men det är möjligt att en aktiv postlåda och en mjuk borttagna postlåda kan ha samma primära SMTP-adress.</span><span class="sxs-lookup"><span data-stu-id="a6441-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="a6441-135">Skapa en In-Place och placera den på den mjukt borttagna postlådan.</span><span class="sxs-lookup"><span data-stu-id="a6441-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="a6441-136">I det här exemplet anges ingen varaktighet för håll.</span><span class="sxs-lookup"><span data-stu-id="a6441-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="a6441-137">Det innebär att objekt kommer att hållas kvar ett obestämt tidsbestämt tidsenligt sätt eller tills det att det är ett väntande objekt tas bort från den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="a6441-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="a6441-138">Du kan också ange varaktigheten för att hålla på plats när du In-Place varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="a6441-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="a6441-139">Det här exemplet innehåller objekt i den inaktiva postlådan i ungefär 7 år.</span><span class="sxs-lookup"><span data-stu-id="a6441-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="a6441-140">Efter en liten stund kör du något av följande kommandon för att verifiera att den mjukt borttagna postlådan är en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="a6441-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="a6441-141">Eller</span><span class="sxs-lookup"><span data-stu-id="a6441-141">Or</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="a6441-142">Mer information</span><span class="sxs-lookup"><span data-stu-id="a6441-142">More information</span></span>

<span data-ttu-id="a6441-143">När du gör en mjuk borttagna postlåda till en inaktiv postlåda kan du hantera postlådan på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="a6441-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="a6441-144">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a6441-144">For more information, see:</span></span>

- [<span data-ttu-id="a6441-145">Ändra kvarhållningstiden för en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="a6441-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="a6441-146">Återställa en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="a6441-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="a6441-147">Återställa en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="a6441-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="a6441-148">[Ta bort en inaktiv postlåda](delete-an-inactive-mailbox.md) (genom att ta bort brytningen)</span><span class="sxs-lookup"><span data-stu-id="a6441-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>