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
ms.openlocfilehash: 6e3bf4c84e7a762f7f54f42ff61f0fbdb9dc1edd
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215510"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Visa och släppa meddelanden i karantän från delade postlådor

> [!NOTE]
> Funktionerna som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.

Användare kan hantera meddelanden i karantän där de är en av mottagarna enligt beskrivningen i Hitta och släppa meddelanden i karantän [som en användare i EOP.](find-and-release-quarantined-messages-as-a-user.md) Men hur blir det med delade postlådor där användaren har behörigheten Fullständig åtkomst och Skicka som eller Skicka för till postlådan enligt beskrivningen i Delade postlådor [i Exchange Online?](/exchange/collaboration-exo/shared-mailboxes)

Tidigare var möjligheten för användare att hantera meddelanden i karantän som skickades till en delad postlåda obligatoriska administratörer för att lämna automatisk mappning aktiverad för den delade postlådan (det är aktiverat som standard när en administratör ger en användare åtkomst till en annan postlåda). Men beroende på storleken på och antalet postlådor som användaren har tillgång till  kan prestandan drabbas av problem när Outlooks försöker öppna alla postlådor som användaren har åtkomst till. Därför väljer många administratörer att ta bort [automatisk mappning för delade postlådor.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Automatisk mappning krävs nu inte längre för att användare ska kunna hantera meddelanden i karantän som har skickats till delade postlådor. Det fungerar bara. Det finns två olika metoder för att komma åt meddelanden i karantän som har skickats till en delad postlåda:

- Om administratören har aktiverat [skräppost-aviseringar](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) för slutanvändare i principer mot skräppost kan alla användare som har åtkomst  till skräppost-aviseringarna för slutanvändaren i den delade postlådan klicka på knappen Granska i meddelandet för att gå till karantän i säkerhets- och &-efterlevnadscentret. Observera att den här metoden endast gör att användare kan hantera meddelanden i karantän som har skickats till den delade postlådan. Användare kan inte hantera sina egna karantänmeddelanden i det här sammanhanget.

- Användaren kan [gå till karantänen i säkerhets- & kompatibilitetscentret.](find-and-release-quarantined-messages-as-a-user.md) Som standard visas endast meddelanden som skickats till användaren. Däremot kan användaren ändra sorteringsresultatet **(knappen**  **Meddelande-ID** som standard) till Mottagarens e-postadress, ange den delade postlådans e-postadress och sedan klicka på Uppdatera för att se meddelanden i karantän som har skickats till den delade postlådan. 

  ![Sortera meddelanden i karantän efter mottagarens e-postadress.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Oavsett metod kan användarna undvika förvirring genom att lägga till kolumnen **Mottagare för** meddelanden i karantän. Max antal kolumner som ska visas är 7, så användaren måste klicka på Ändra kolumner **,** ta bort en befintlig kolumn (till exempel **principtyp**), välja Mottagare och sedan klicka på **Spara** eller **Spara som standard.** 

  ![Ta bort kolumnen Principtyp och lägg till kolumnen Mottagare i karantän.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Saker att tänka på

- Den första användaren som agerar på det i karantän-meddelandet avgör meddelandets första dag för alla som använder den delade postlådan. Om till exempel en delad postlåda används av 10 användare och en användare tar bort karantänmeddelandet, tas meddelandet bort för alla tio användare. Om en användare väljer att släppa meddelandet släpps det till den delade postlådan och är tillgängligt för alla andra användare av den delade postlådan.

- Knappen Spärra **avsändare är för** närvarande inte tillgänglig i den utfällna informationen för meddelanden i karantän som har skickats till den delade postlådan. 

- Om karantänåtgärder för delade postlådor rekommenderar vi att du inte har fler än två nivåer med kapslade grupper om du använder kapslade säkerhetsgrupper för att bevilja åtkomst till en delad postlåda. Till exempel är Grupp A medlem i Grupp B, som är medlem i Grupp C. Om du vill tilldela behörigheter till en delad postlåda ska du inte lägga till användaren i Grupp A och sedan tilldela grupp C till den delade postlådan.  

- För att hantera meddelanden i karantän för den delade postlådan i [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)måste slutanvändaren använda cmdlet:en [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) med en delad postlådas e-postadress för parameterns _RecipientAddress-värde_ för att identifiera meddelandena. Till exempel:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Därefter kan slutanvändaren välja ett meddelande i karantän i listan som ska visas eller vidta åtgärder för.

  Det här exemplet visar alla meddelanden i karantän som har skickats till den delade postlådan och släpper sedan det första meddelandet i listan från karantän (det första meddelandet i listan är 0, det andra är 1 och så vidare).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Detaljerad information om syntax och parametrar finns i följande artiklar:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
