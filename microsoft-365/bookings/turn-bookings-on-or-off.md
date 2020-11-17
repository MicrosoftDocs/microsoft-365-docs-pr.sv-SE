---
title: Aktivera eller inaktivera Microsoft-bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lär dig hur du får till gång till Microsoft-bokningar i Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126606"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Aktivera eller inaktivera Microsoft-bokningar

Du kan aktivera eller inaktivera bokningar för hela organisationen eller för specifika användare. När du aktiverar bokningar för användare kan de skapa en sida med information, skapa en kalender och låta andra boka tid med dem.

> [!NOTE]
> Administratörs kontrollerna som beskrivs i dessa avsnitt är inte tillgängliga för Office 365 som drivs av 21Vianet-kunder (Kina).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Aktivera eller inaktivera bokningar för organisationen med hjälp av administrations centret för Microsoft 365

1. Logga in på administrations centret för Microsoft 365 som global administratör.

2. I administrations centret går du till  **Inställningar**   \> **organisations inställningar** och väljer **bokningar**.

3. Markera kryss rutan för **Låt organisationen använda bokningar** för att aktivera eller inaktivera bokningar för din organisation.

   > [!NOTE]
   > Om du stänger av bokningarna inaktive ras all åtkomst till tjänsten, inklusive skapande och hantering av boknings sidor.

4. Välj **Spara ändringar**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Aktivera eller inaktivera bokningar för organisationen med hjälp av PowerShell

Om du vill aktivera eller inaktivera bokningar för din organisation med PowerShell-cmdleten [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) [ansluter du till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Aktivera eller inaktivera bokningar för enskilda användare

Du kan inaktivera bokningar för enskilda användare.

1. Gå till administrations centret för Microsoft 365 och välj **användare** \> **aktiva användare**.

1. Välj önskad användare och sedan **licenser och appar**.

1. Expandera **appar** och avmarkera kryss rutan för Microsoft-bokningar.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Kräv godkännande från personalen innan du delar ledig/upptagen-information

Administratörer kan kräva att de anställda deltar i sin organisation innan de kan använda sin tillgänglighets information för att bli bookable via en boknings sida. Den här inställningen är tillgänglig i administrations centret för Microsoft 365 under **Inställningar** \> **Settings** \> **Bookings**.

När den här inställningen är aktive rad kommer anställda som har lagts till som personal i boknings kalendrar att hitta en av länkarna acceptera/avvisa i e-postmeddelandet.

Den här funktionen lanseras gradvis till Microsoft 365-kunder. Om det här alternativet inte visas i administrations centret för Microsoft 365, kom tillbaka snart.

## <a name="block-social-sharing-options"></a>Blockera alternativ för sociala delning

Administratörer kan styra hur boknings sidor delas i sociala nätverk. Den här inställningen är tillgänglig i administrations centret för Microsoft 365 under **Inställningar** \> **Settings** \> **Bookings**.

Den här funktionen lanseras gradvis till Microsoft 365-kunder. Om det här alternativet inte visas i administrations centret för Microsoft 365, kom tillbaka snart.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Tillåt endast valda användare att skapa kalender kalendrar

Genom att använda princip begränsningar kan du begränsa licensierade användare från att kunna skapa kalender kalendrar. Du måste först aktivera bokningar för hela organisationen. Alla användare i organisationen får boka licenser, men bara de som ingår i policyn kan skapa kalender kalendrar och ha fullständig kontroll över vem som får till gång till de kalendrar de skapar.

Användare som ingår i den här principen kan skapa nya kalender kalendrar och kan läggas till som personal i valfri kapacitet (inklusive administratörs rollen) för befintliga kalender kalendrar. Användare som inte ingår i den här principen kan inte skapa nya kalender kalendrar och får ett fel meddelande om de försöker göra det.

Du måste köra följande kommandon med Exchange Online PowerShell. Mer information om hur du kör Exchange Online-cmdlets finns i [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> I stegen nedan förutsätts det att inga andra principer för Outlook Web App (OWA)-postlådor har skapats i organisationen.

1. Skapa en ny post låda för användare som ska få tillåtelse att skapa kalender kalendrar. (Det går att skapa en ny post låda i kalendern i kalendrar).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Mer information finns i [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Koppla den här principen till relevanta användare genom att köra det här kommandot för varje användare som du vill ge behörighet att skapa kalender kalendrar.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Mer information finns i [set-CASMailbox cmdlethttps](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Valfritt: kör det här kommandot om du vill inaktivera bokningar för alla andra användare i organisationen.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Mer information finns i [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Mer information om principer för OWA-postlådor finns i följande avsnitt:

- [Skapa en Outlook-princip för en post låda i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Använda eller ta bort en Outlook-princip på en post låda i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
