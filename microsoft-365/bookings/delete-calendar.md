---
title: Ta bort en bokningskalender
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Använd administrationscentret Microsoft 365 eller den Windows PowerShell ta bort Bookings-kalendrar.
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034097"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="8cee9-103">Ta bort en bokningskalender i Bookings</span><span class="sxs-lookup"><span data-stu-id="8cee9-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="8cee9-104">I den här artikeln förklaras hur du tar bort en oönskad bokningskalender.</span><span class="sxs-lookup"><span data-stu-id="8cee9-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="8cee9-105">Du kan ta bort bokningskalendern i Microsoft 365 administrationscenter eller så kan du använda PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cee9-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="8cee9-106">Bookings-kalendern är en postlåda i Exchange Online så du tar bort motsvarande användarkonto för att ta bort bokningskalendern.</span><span class="sxs-lookup"><span data-stu-id="8cee9-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cee9-107">Alla bokningskalendrar som du skapade 2017 eller tidigare måste tas bort med PowerShell-instruktionerna för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8cee9-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="8cee9-108">Alla bokningskalendrar som skapades 2018 eller senare kan tas bort Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8cee9-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="8cee9-109">Bokningskalendern är den plats där all relevant information om bokningskalendern och bokningsdata lagras, inklusive:</span><span class="sxs-lookup"><span data-stu-id="8cee9-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="8cee9-110">Företagsinformation, logotyp och arbetstid som lades till när bokningskalendern skapades</span><span class="sxs-lookup"><span data-stu-id="8cee9-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="8cee9-111">Relevant personal och tjänster som lades till när bokningskalendern skapades</span><span class="sxs-lookup"><span data-stu-id="8cee9-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="8cee9-112">Alla bokningar och återkommande avtalade tider läggs till i bokningskalendern när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="8cee9-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="8cee9-113">När en bokningskalender tas bort tas denna ytterligare information också bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="8cee9-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8cee9-114">Ta bort en bokningskalender Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="8cee9-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8cee9-115">Gå till administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8cee9-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="8cee9-116">Välj **Användare** i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="8cee9-116">In the Admin center, select **Users**.</span></span>

   ![Bild av användargränssnittet för användare Microsoft 365 administrationscentret](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="8cee9-118">På sidan **Aktiva användare** väljer du namnen på de användare du vill ta bort och väljer sedan **Ta bort användare**.</span><span class="sxs-lookup"><span data-stu-id="8cee9-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Bild av ta bort användargränssnittet i Microsoft 365 administrationscenter](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="8cee9-120">Ta bort en bokningskalender med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cee9-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="8cee9-121">Se [Anslut för Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) för krav och vägledning för anslutning till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cee9-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="8cee9-122">Om du vill utföra de här stegen måste du använda ett aktivt Microsoft PowerShell-kommandofönster som du kör genom att välja alternativet "Kör som administratör".</span><span class="sxs-lookup"><span data-stu-id="8cee9-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="8cee9-123">I ett PowerShell-fönster läser du in EXO V2-modulen genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8cee9-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="8cee9-124">Om du redan har [installerat EXO V2-modulen](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)fungerar det föregående kommandot som det är skrivet.</span><span class="sxs-lookup"><span data-stu-id="8cee9-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="8cee9-125">Följande syntax används för kommandot du behöver köra:</span><span class="sxs-lookup"><span data-stu-id="8cee9-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="8cee9-126">_\<UPN\>_ är ditt konto i formatet användarnamn (t.ex. `john@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="8cee9-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="8cee9-127">När du uppmanas att göra det loggar du in med autentiseringsuppgifterna för klientorganisationen Microsoft 365 klientorganisationen som är värd för den bokningskalender du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="8cee9-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="8cee9-128">När det här kommandot har körts klart anger du följande kommando för att få en lista över bokningspostlådor i klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="8cee9-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="8cee9-129">Skriv följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8cee9-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="8cee9-130">Var noga med att skriva det exakta namnet på det bokningsalias som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="8cee9-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="8cee9-131">Ange följande kommando för att verifiera att kalendern har tagits bort:</span><span class="sxs-lookup"><span data-stu-id="8cee9-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="8cee9-132">Den borttagna kalendern visas inte i utdata.</span><span class="sxs-lookup"><span data-stu-id="8cee9-132">The deleted calendar will not appear in the output.</span></span>
