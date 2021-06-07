---
title: Lägg till personal i Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Använd den här sidan för att skapa en personallista och hantera personalinformation som namn, telefonnummer och e-postadress.
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768951"
---
# <a name="add-staff-to-bookings"></a>Lägg till personal i Bookings

På sidan Personal i Bookings skapar du en personallista och hanterar personalinformation som namn, telefonnummer och e-postadress. Här kan du också ange arbetstider för varje anställd.

## <a name="before-you-begin"></a>Innan du börjar

Även om Bookings är en Microsoft 365 är det inte alla anställda som måste ha ett Microsoft 365 konto. Alla anställda måste ha en giltig e-postadress för att kunna ta emot bokningar och schemalägga ändringar.

## <a name="watch-add-your-staff-to-bookings"></a>Titta: Lägg till personal i Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Steg

1. Gå till sidan [Hantera personal och](https://outlook.office.com/bookings/staff) välj Lägg till **personal**

2. Välj knappen **Lägg till** personal.

3. När du lägger till personal från organisationen  skriver du deras namn i fältet Lägg till personer och väljer dem när de visas i den nedrullningrullningade menyn. De andra fälten fylls i automatiskt.

    När en anställd läggs till kan du redigera namnet som visas i alla Bookings-meddelanden genom att välja **x** bredvid namnet och redigera **fältet Lägg till** personer. Det kan vara användbart om du vill att anställda ska få en särskild titel eller ett visst namn för kunder, till exempel att ange Adele Vance som "Dr. Vance, MD".

4. Om du vill lägga till personal utanför organisationen fyller du i deras e-post och annan information manuellt.

    > [!NOTE]
    > Personal utanför klientorganisationen kommer inte att kunna dela ledig/upptagen-information med Bookings.

5. Välj en roll för varje anställd: Administratör, Läsare eller Gäst.
    - **Administratörer** kan redigera alla inställningar, lägga till och ta bort personal samt skapa, redigera och ta bort bokningar.
    - **Läsare** kan se alla bokningar i kalendern, men de kan inte ändra eller ta bort dem. De har skrivskyddade åtkomst till inställningar.
    - **Gäster** kan tilldelas till bokningar, men de kan inte öppna bokningspostlådan.

6. Välj **Meddela all personal via e-post när en bokning som tilldelats dem skapas eller ändras för att** aktivera personal-e-post. Följande är ett exempel på ett e-postmeddelande:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Ett e-postmeddelande från Bookings":::

7. Välj **Händelser Office 365** kalendern påverkar tillgängligheten om du vill att ledig/upptagen-information från personalens kalendrar ska påverka tillgängligheten för bookings-tjänster via Bookings.

    Om en anställd till exempel har ett gruppmöte eller en personlig avtalad tid schemalagd till 15:00 på en onsdag, visar Bookings att den anställde inte kan bokas på den platsen. Den tiden visas som upptagen eller preliminär i kalendervyn i Bookings, som i exemplet nedan.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="En vy av en Bookings-kalender":::

> [!IMPORTANT]
> Vi rekommenderar att du lämnar den här inställningen på (den är aktiverad som standard) för att undvika dubbelbokningar och för att optimera tillgängligheten för personalen.

8. Välj **Använd öppettider om** du vill ange alla bokningsbara tider för de anställda  så att de bara ligger inom den arbetstid som du anger i avsnittet Öppettider på sidan Företagsinformation.

    Genom att avmarkera den här rutan kan personalen ges anpassade timmar som ytterligare begränsar när de kan bokas. Det här är användbart för scenarier där en anställd kanske bara är på plats tisdagar och onsdagar, eller de ägna sina morgonar åt en typ av avtalade tider och deras på eftermiddagen för andra typer.

    > [!NOTE]
    > När du tilldelar personal till en tjänst är det bara de 31 första anställda som du lägger till på personalsidan som visas.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Göra en Bookings-användare till superanvändare utan att lägga till dem som personal i Bookings

Du kanske vill lägga till en person i personallistan i Bookings utan att göra dem tillgängliga för kunder eller kunder. När du gör dem till superanvändare blir de administratör för bokningspostlådan. Att vara administratör för en bokningspostlåda definieras som att ha fullständig åtkomst och behörighet att skicka som till bokningspostlådan.

> [!NOTE]
> De här stegen fungerar bara om den användare som läggs till inte redan har tilldelats en **visningsroll** i Bookings.

1. [Anslut att Microsoft 365 med PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Tilldela fullständig åtkomst med följande kommandon med hjälp av PowerShell:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Kör sedan det här kommandot för att tilldela behörigheten Skicka som.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Här är ett exempel på PowerShell-kommando för att lägga till Allie Bellew i Contosos dagkalenders bokningspostlåda.

1. Kör först det här kommandot:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. Kör sedan det här kommandot:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Nu har Allie Bellew** administratörsåtkomst, men visas inte som bokbar personal i Bookings.
