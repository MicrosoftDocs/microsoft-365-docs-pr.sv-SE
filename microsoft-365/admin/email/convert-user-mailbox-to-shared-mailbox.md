---
title: Konvertera en användarpostlåda till en delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Lär dig hur du konverterar en privat post låda till en delad post låda som kan användas av flera användare. '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445693"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Konvertera en användarpostlåda till en delad postlåda

När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern. Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person. Vid ett senare datum kan du konvertera en delad post låda tillbaka till en användare (privat) post låda.

**Här är några viktiga saker som du måste känna till:**

- Den användar post låda som du försöker att konvertera måste ha tilldelats en licens innan du konverterar den till en delad post låda. Annars visas inte alternativet för att konvertera postlådan. Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan. När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.

- Delade post lådor kan ha upp till 50 GB data utan licens tilldelade till dem. Om du vill ha mer information än den måste du ha en tilldelad licens. Du kan behöva ta bort många e-postmeddelanden (till exempel till bilagor) från den delade post lådan för att krympa dem så att du kan ta bort licensen.

- Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).

- Reglerna är intakta efter att post lådan konverterats till en delad post låda.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Använda administrations centret för Exchange för att konvertera en post låda
 
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **mottagarnas** \> **post lådor**.

3. Välj användarens post låda. Välj **konvertera**under **konvertera till delad post låda**.

4. Om post lådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den. Ta inte bort användarens konto. Den delade postlådan behöver ha den som en fästpunkt. Om du konverterar post lådan för en anställd som lämnar din organisation bör du vidta ytterligare åtgärder för att se till att de inte längre kan logga in. Se [ta bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Det är inte nödvändigt att återställa användarens lösen ord under konvertering av post låda. Men om lösen ordet inte återställs **fortsätter det ursprungliga användar namnet och lösen ordet efter att** post lådans konvertering är klar.

Om du behöver veta mer om delade post lådor läser du [om delade post lådor](about-shared-mailboxes.md) och [skapar en delad post låda](create-a-shared-mailbox.md).

> [!NOTE]
> Inga separata licenser krävs för delade post lådor. Om du däremot vill aktivera In-Place arkiv eller skicka ett In-Place undantag eller en tvist i en delad post låda måste du tilldela en Exchange Online-prenumeration 1 med Exchange Online-arkivering eller Exchange Online abonnemang 2-licens till post lådan.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Konvertera en borttagen användares postlåda

Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:

1. [Återställ användarens konto](../add-users/restore-user.md).

2. Kontrol lera att en Microsoft 365-licens har tilldelats till den.

3. Återställ användarens lösen ord.
    
4. Vänta i 20-30 minuter på att postlådan återskapas.
    
5. Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.
    
6. När det är klart kan du ta bort licensen från användarens post låda. Ta inte bort användarens gamla postlåda. Den delade postlådan behöver ha den som en fästpunkt.
    
7. Lägg till medlemmar för den delade postlådan.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Konvertera en delad post låda tillbaka till en användares (privat) post låda

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
   
2. Välj **Recipients** \> **delade**mottagare.

3. Välj den delade post lådan. Välj **konvertera**under **konvertera till vanlig post låda**.

4. Gå tillbaka till administrations centret. Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**. Tilldela en licens till kontot och återställ lösenordet.

   Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Konvertera en användares postlåda i en hybridmiljö

Om den delade post lådan är i en hybrid miljö **rekommenderar** vi att (nästan behöva!) du flyttar tillbaka användar post lådan till en delad post låda och sedan flyttar tillbaka den delade post lådan till molnet. 

Så här gör du för att: om du konverterar post lådan i molnet kan den konverteras, men lokala användare tycker fortfarande att post lådan är post lådan, eftersom den nya verkligheten inte synkroniserar tillbaka till lokala platser.

Vanligt vis är det här inget problem, men det finns några scenarier där de lokala attributen (som tror att post lådan är användarens post låda) kan skriva över de nya moln versionerna av dessa attribut och det kan leda till att post lådan konverteras tillbaka. Det här är ett problem med att användar post lådor kräver licenser **eller att de är mjuka borttagna efter 30 dagar**!

Vi har åtgärdat de flesta skälen till att det här gäller, men det kan ändå inträffa, trots att det inte är ofta. Det bästa är att vara säkert och flytta tillbaka post lådan till lokal, konvertera den och sedan flytta tillbaka den delade post lådan till molnet. Den rekommenderade lösningen är inte ett brott mot licens avtalet för Hybrid miljöer eftersom förekomsten av användar post lådan är bara tillfällig. Du strider mot din licens om du bihörde användar post lådan eller den delade post lådan i din lokala organisation och inte flyttade den tillbaka till molnet.

> [!NOTE]
> Om du är medlem i roll gruppen organisations hantering eller mottagare kan du använda Exchange Management Shell för att ändra en användar post låda till en delad post låda lokalt. Till exempel `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Se lösningen i den här support lösningen för instanser när [delade post lådor oväntat omvandlas till användar post lådor](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).
  
## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
