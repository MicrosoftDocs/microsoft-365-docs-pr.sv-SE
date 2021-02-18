---
title: Visa och släppa meddelanden i karantän från delade postlådor
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Användare kan lära sig hur de visar och agerar på meddelanden i karantän som har skickats till delade postlådor som de har behörighet till.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31fbf9c54c3f28e439f444dde872469918dc29d4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290147"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Visa och släppa meddelanden i karantän från delade postlådor

> [!NOTE]
> De funktioner som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.

Användare kan hantera meddelanden i karantän där de är en av mottagarna enligt beskrivningen i Hitta och släppa meddelanden i karantän [som användare i EOP.](find-and-release-quarantined-messages-as-a-user.md) Men hur blir det med delade postlådor där användaren har behörigheten Fullständig åtkomst och Skicka som eller Skicka för till postlådan enligt beskrivningen i Delade postlådor [i Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

Tidigare var möjligheten för användare att hantera meddelanden i karantän som skickas till en delad postlåda obligatoriska administratörer för att lämna automatisk mappning aktiverad för den delade postlådan (den är aktiverad som standard när en administratör ger en användare åtkomst till en annan postlåda). Men prestandan kan drabbas av prestandan, beroende på storleken på och antalet  postlådor som användaren har tillgång till, när Outlook försöker öppna alla postlådor som användaren har åtkomst till. Därför väljer många administratörer att ta bort [automatisk mappning för delade postlådor.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Automatisk mappning krävs nu inte längre för att användare ska kunna hantera meddelanden i karantän som har skickats till delade postlådor. Det fungerar bara. Det finns två olika metoder för att komma åt meddelanden i karantän som har skickats till en delad postlåda:

- Om administratören har aktiverat [skräppost-aviseringar](configure-your-spam-filter-policies.md) för slutanvändare i principer för skräppostskydd kan alla användare som har  åtkomst till slutanvändarens skräppost-aviseringar i den delade postlådan klicka på knappen Granska i meddelandet för att gå till karantän i Säkerhets- & efterlevnadscenter. Den här metoden gör det bara möjligt för användare att hantera meddelanden i karantän som har skickats till den delade postlådan. Användare kan inte hantera sina egna karantänmeddelanden i det här sammanhanget.

- Användaren kan [gå till karantänen i säkerhets- & Efterlevnadscenter.](find-and-release-quarantined-messages-as-a-user.md) Som standard visas endast meddelanden som har skickats till användaren. Användaren kan ändra sorteringsresultatet **(knappen**  **Meddelande-ID** som standard) till Mottagarens e-postadress, ange den delade postlådans e-postadress och sedan klicka på Uppdatera för att se meddelanden i karantän som har skickats till den delade postlådan. 

  ![Sortera meddelanden i karantän efter mottagarens e-postadress.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Oavsett metod kan användarna undvika förvirring genom att lägga till kolumnen **Mottagare för** meddelanden i karantän. Max antal kolumner som ska visas är 7, så användaren måste klicka på Ändra kolumner, ta bort en  befintlig kolumn (till exempel principtyp), välja Mottagare och sedan klicka på Spara eller Spara som **standard.**  

  ![Ta bort kolumnen Principtyp och lägg till kolumnen Mottagare i karantän.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Saker att tänka på

- Den första användaren som agerar på det meddelande i karantän som bestämmer den första användaren av meddelandet för alla som använder den delade postlådan. Om till exempel en delad postlåda används av tio användare och en användare väljer att ta bort karantänmeddelandet, tas meddelandet bort för alla tio användare. Om en användare väljer att släppa meddelandet släpps det till den delade postlådan och är tillgängligt för alla andra användare av den delade postlådan.

- Knappen Spärra **avsändare är för** närvarande  inte tillgänglig i den utfällna informationen för meddelanden i karantän som har skickats till den delade postlådan.

- För att hantera meddelanden i karantän för den delade postlådan i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)måste slutanvändaren använda cmdleten [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) med en delad postlådas e-postadress för värdet på parametern _RecipientAddress_ för att identifiera meddelandena. Till exempel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Slutanvändaren kan sedan välja ett meddelande i karantän i listan som du vill visa eller vidta åtgärder för.

  Det här exemplet visar alla meddelanden i karantän som skickades till den delade postlådan och släpper sedan det första meddelandet i listan från karantän (det första meddelandet i listan är 0, det andra är 1 och så vidare).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Detaljerad information om syntax och parametrar finns i följande artiklar:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
