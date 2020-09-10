---
title: Ta bort en boknings kalender
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Använd administrations centret för Microsoft 365 eller Windows PowerShell för att ta bort kalendrar.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422448"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="01a21-103">Ta bort en boknings kalender i bokningar</span><span class="sxs-lookup"><span data-stu-id="01a21-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="01a21-104">I den här artikeln förklarar vi hur du kan ta bort en oönskad boknings kalender.</span><span class="sxs-lookup"><span data-stu-id="01a21-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="01a21-105">Du kan ta bort boknings kalendern i administrations centret för Microsoft 365 eller så kan du använda PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01a21-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="01a21-106">Kalender kalendrar är en post låda i Exchange Online så du tar bort ett motsvarande användar konto för att ta bort boknings kalendern.</span><span class="sxs-lookup"><span data-stu-id="01a21-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01a21-107">Alla boknings kalendrar som du skapade i 2017 eller tidigare måste tas bort med hjälp av PowerShell-instruktionerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="01a21-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="01a21-108">Alla boknings kalendrar som skapats i 2018 eller efter kan tas bort i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01a21-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="01a21-109">I boknings kalendern är det viktigt att all relevant information om kalender och data lagras, inklusive:</span><span class="sxs-lookup"><span data-stu-id="01a21-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="01a21-110">Företags information, logo typ och arbets tider som lagts till när boknings kalendern skapades</span><span class="sxs-lookup"><span data-stu-id="01a21-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="01a21-111">Relevant personal och tjänster som läggs till när boknings kalendern skapades</span><span class="sxs-lookup"><span data-stu-id="01a21-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="01a21-112">Alla bokningar och ledig tid för avtalade tider har lagts till i boknings kalendern när den skapades.</span><span class="sxs-lookup"><span data-stu-id="01a21-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="01a21-113">När en boknings kalender raderas tas denna ytterligare information bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="01a21-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="01a21-114">Ta bort en boknings kalender i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01a21-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="01a21-115">Gå till administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01a21-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="01a21-116">Välj **Användare** i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="01a21-116">In the Admin center, select **Users**.</span></span>

   ![Bild av användar gränssnittet i Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="01a21-118">På sidan **Aktiva användare** väljer du namnen på de användare du vill ta bort och väljer sedan **Ta bort användare**.</span><span class="sxs-lookup"><span data-stu-id="01a21-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Bild av användar gränssnittet ta bort i Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="01a21-120">Ta bort en boknings kalender med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="01a21-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="01a21-121">Se [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) för förutsättningar och vägledning för anslutning till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01a21-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="01a21-122">För att utföra de här stegen måste du använda ett aktivt Microsoft PowerShell-Kommandotolken som du körde genom att välja alternativet Kör som administratör.</span><span class="sxs-lookup"><span data-stu-id="01a21-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="01a21-123">Ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="01a21-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="01a21-124">När du uppmanas att göra det loggar du in med autentiseringsuppgifter för klient organisation för Microsoft 365-klienten som är värd för den boknings kalender du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="01a21-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="01a21-125">I kommando tolken för PowerShell anger du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="01a21-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="01a21-126">Ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="01a21-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="01a21-127">När det här kommandot har körts klart anger du följande kommando för att få en lista över bokningspostlådor i klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="01a21-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="01a21-128">Skriv följande kommando:</span><span class="sxs-lookup"><span data-stu-id="01a21-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="01a21-129">Var försiktig så att du skriver det exakta namnet på det alias som du vill ta bort permanent.</span><span class="sxs-lookup"><span data-stu-id="01a21-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="01a21-130">Om du vill kontrol lera att kalendern har tagits bort skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="01a21-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="01a21-131">Den borttagna kalendern visas inte i resultatet.</span><span class="sxs-lookup"><span data-stu-id="01a21-131">The deleted calendar will not appear in the output.</span></span>
