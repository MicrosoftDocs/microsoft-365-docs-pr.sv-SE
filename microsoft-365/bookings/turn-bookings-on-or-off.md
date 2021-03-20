---
title: Aktivera eller inaktivera Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lär dig hur du får tillgång till Microsoft Bookings i Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913772"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Aktivera eller inaktivera Microsoft Bookings

Bookings kan aktiveras eller inaktiveras för hela organisationen eller för specifika användare. När du aktiverar Bookings för användare kan de skapa en bookings-sida, skapa en kalender och ge andra möjlighet att boka tid med dem.

> [!NOTE]
> Administratörskontrollerna som beskrivs i de här avsnitten är inte tillgängliga för kunder av Office 365 som drivs av 21Vianet (Kina).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Aktivera eller inaktivera Bookings för din organisation med hjälp av administrationscentret för Microsoft 365

1. Logga in i administrationscentret för Microsoft 365 som global administratör.

2. Gå till Inställningar Organisationsinställningar i  ****   \> **administrationscentret och** välj **Bookings.**

3. Markera kryssrutan för Tillåt **din organisation att använda Bookings för** att aktivera eller inaktivera Bookings för din organisation.

   > [!NOTE]
   > Om du inaktiverar Bookings inaktiveras all åtkomst till tjänsten, inklusive skapande och hantering av Bookings-sidor.

4. Välj **Save Changes**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Aktivera eller inaktivera Bookings för din organisation med PowerShell

Så här aktiverar eller inaktiverar du Bookings för organisationen med PowerShell-cmdleten [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Aktivera eller inaktivera Bookings för enskilda användare

Du kan inaktivera Bookings för enskilda användare.

1. Gå till administrationscentret för Microsoft 365 och välj sedan **Användare** \> **aktiva användare.**

1. Välj önskad användare och välj sedan **Licenser och appar.**

1. Expandera **Appar** och avmarkera kryssrutan för Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Kräva godkännande av personal innan du delar ledig/upptagen-information

Administratörer kan kräva att anställda i organisationen anmäler sig innan deras tillgänglighetsinformation delas via Bookings och innan de kan bokas via en bokningssida. Den här inställningen är tillgänglig i administrationscentret för Microsoft 365 under **Inställningar** \> **Inställningar** \> **Bookings.**

När den här inställningen är aktiverad hittar anställda som lagts till som personal i bokningskalendrar länken Godkänn/Avvisa i e-postmeddelandet som de får.

Den här funktionen lanseras gradvis över hela världen till Microsoft 365-kunder. Om du inte ser det här alternativet i administrationscentret för Microsoft 365 kommer du snart tillbaka.

## <a name="block-social-sharing-options"></a>Blockera alternativ för social delning

Administratörer kan styra hur bokningssidor delas i sociala nätverk. Den här inställningen är tillgänglig i administrationscentret för Microsoft 365 under **Inställningar** \> **Inställningar** \> **Bookings.**

Den här funktionen lanseras gradvis över hela världen till Microsoft 365-kunder. Om du inte ser det här alternativet i administrationscentret för Microsoft 365 kommer du snart tillbaka.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Tillåt endast vissa användare att skapa bookings-kalendrar

Genom att använda principbegränsningar kan du begränsa licensierade användare från att skapa Bookings-kalendrar. Du måste först aktivera Bookings för hela organisationen. Alla användare i organisationen har bookings-licenser, men endast de som ingår i principen kan skapa Bookings-kalendrar och har full kontroll över vem som kan komma åt kalendrarna som de skapar.

Användare som omfattas av den här principen kan skapa nya Bookings-kalendrar och kan läggas till som personal med alla funktioner (inklusive administratörsrollen) i befintliga Bookings-kalendrar. Användare som inte omfattas av den här principen kan inte skapa nya Bookings-kalendrar och får ett felmeddelande om de försöker göra det.

Du måste köra följande kommandon med Exchange Online PowerShell. Mer information om hur du kör Exchange Online-cmdlets finns [i Ansluta till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> I stegen nedan förutsätts att inga andra Outlook Web App-postlådeprinciper (OWA) har skapats i organisationen.

1. Skapa en ny postlådeprincip för användare som ska kunna skapa Bookings-kalendrar. (Som standard tillåts kalenderskapande i Bookings av nya postlådeprinciper.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Mer information finns i [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Tilldela den här principen till relevanta användare genom att köra det här kommandot för varje användare som du vill ge behörighet att skapa Bookings-kalendrar.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Mer information finns i [Set-CASMailbox.](/powershell/module/exchange/set-casmailbox)

3. Valfritt: Kör det här kommandot om du vill inaktivera Bookings för alla andra användare i organisationen.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Mer information finns i [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)

Mer information om OWA-postlådeprinciper finns i följande avsnitt:

- [Skapa en outlook på webben-postlådeprincip i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Använda eller ta bort en outlook på webben-postlådeprincip för en postlåda i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)