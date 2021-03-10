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
description: Använd administrationscentret för Microsoft 365 eller Windows PowerShell för att ta bort bookingskalendrar.
ms.openlocfilehash: 7407298adb402de79a1010b51544deee4b94cf5a
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604026"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Ta bort en bokningskalender i Bookings

I den här artikeln förklaras hur du tar bort en oönskad bokningskalender. Du kan ta bort bokningskalendern i administrationscentret för Microsoft 365 eller använda PowerShell. Kalendern i Bookings är en postlåda i Exchange Online så du tar bort motsvarande användarkonto för att ta bort bokningskalendern.

> [!IMPORTANT]
> Alla bokningskalendrar som du skapade under 2017 eller tidigare måste tas bort med hjälp av PowerShell-instruktionerna för det här avsnittet. Alla bokningskalendrar som skapades under 2018 eller senare kan tas bort i administrationscentret för Microsoft 365.

I bokningskalendern lagras all relevant information om bokningskalendern och bokningsdata, inklusive:

- Företagsinformation, logotyp och arbetstid som lades till när bokningskalendern skapades
- Relevant personal och tjänster som lades till när bokningskalendern skapades
- Alla bokningar och återkommande avtalade tider läggs till i bokningskalendern när den har skapats.

> [!WARNING]
> När en bokningskalender tas bort tas den här informationen också bort permanent och kan inte återställas.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Ta bort en bokningskalender i administrationscentret för Microsoft 365

1. Gå till administrationscentret för Microsoft 365.

1. Välj **Användare** i administrationscentret.

   ![Bild av användargränssnittet för användare i administrationscentret för Microsoft 365](../media/bookings-admin-center-users.png)

1. På sidan **Aktiva användare** väljer du namnen på de användare du vill ta bort och väljer sedan **Ta bort användare**.

   ![Bild av användargränssnittet för Ta bort användare i administrationscentret för Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Ta bort en bokningskalender med Exchange Online PowerShell

Se [Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) för krav och vägledning för anslutning till Exchange Online PowerShell.

För att utföra de här stegen måste du använda ett aktivt Microsoft PowerShell-kommandofönster som du kör genom att välja alternativet "Kör som administratör".

1. I ett PowerShell-fönster laddar du EXO V2-modulen genom att köra följande kommando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Om du redan har [installerat EXO V2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)fungerar det föregående kommandot som det är skrivet.
   
2. Följande syntax används för kommandot du behöver köra:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ är ditt konto i huvudnamnsformat (till `john@contoso.com` exempel).

3. När du uppmanas till det loggar du in med autentiseringsuppgifter som innehavaradministratör på Microsoft 365-klienten som är värd för den bokningskalender du vill ta bort permanent.

4. När det här kommandot har körts klart anger du följande kommando för att få en lista över bokningspostlådor i klientorganisationen:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. Skriv följande kommando:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Var noga med att skriva det exakta namnet på det bokningspostlådealias som du vill ta bort permanent.

6. Bekräfta att kalendern har tagits bort genom att ange följande kommando:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   Den borttagna kalendern visas inte i utdata.
