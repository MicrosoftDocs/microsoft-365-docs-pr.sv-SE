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
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126655"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Ta bort en boknings kalender i bokningar

I den här artikeln förklarar vi hur du kan ta bort en oönskad boknings kalender. Du kan ta bort boknings kalendern i administrations centret för Microsoft 365 eller så kan du använda PowerShell. Kalender kalendrar är en post låda i Exchange Online så du tar bort ett motsvarande användar konto för att ta bort boknings kalendern.

> [!IMPORTANT]
> Alla boknings kalendrar som du skapade i 2017 eller tidigare måste tas bort med hjälp av PowerShell-instruktionerna i det här avsnittet. Alla boknings kalendrar som skapats i 2018 eller efter kan tas bort i administrations centret för Microsoft 365.

I boknings kalendern är det viktigt att all relevant information om kalender och data lagras, inklusive:

- Företags information, logo typ och arbets tider som lagts till när boknings kalendern skapades
- Relevant personal och tjänster som läggs till när boknings kalendern skapades
- Alla bokningar och ledig tid för avtalade tider har lagts till i boknings kalendern när den skapades.

> [!WARNING]
> När en boknings kalender raderas tas denna ytterligare information bort permanent och kan inte återställas.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Ta bort en boknings kalender i administrations centret för Microsoft 365

1. Gå till administrationscentret för Microsoft 365.

1. Välj **Användare** i administrationscentret.

   ![Bild av användar gränssnittet i Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. På sidan **Aktiva användare** väljer du namnen på de användare du vill ta bort och väljer sedan **Ta bort användare**.

   ![Bild av användar gränssnittet ta bort i Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Ta bort en boknings kalender med Exchange Online PowerShell

Se [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) för förutsättningar och vägledning för anslutning till Exchange Online PowerShell.

För att utföra de här stegen måste du använda ett aktivt Microsoft PowerShell-Kommandotolken som du körde genom att välja alternativet Kör som administratör.

1. Ange följande kommando:

   ```PowerShell
    $user = get-credential
   ```

1. När du uppmanas att göra det loggar du in med autentiseringsuppgifter för klient organisation för Microsoft 365-klienten som är värd för den boknings kalender du vill ta bort permanent.

1. I kommando tolken för PowerShell anger du det här kommandot:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Ange följande kommando:

   ```PowerShell
    Import-PSSession $s
   ```

1. När det här kommandot har körts klart anger du följande kommando för att få en lista över bokningspostlådor i klientorganisationen:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Skriv följande kommando:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Var försiktig så att du skriver det exakta namnet på det alias som du vill ta bort permanent.

1. Om du vill kontrol lera att kalendern har tagits bort skriver du följande kommando:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   Den borttagna kalendern visas inte i resultatet.
