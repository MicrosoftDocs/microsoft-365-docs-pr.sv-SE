---
title: Konvertera en användarpostlåda till en delad postlåda
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Lär dig att konvertera en privat postlåda till en delad postlåda som kan nås av flera användare. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811957"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Konvertera en användarpostlåda till en delad postlåda

När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern. Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person. Vid ett senare tillfälle kan du konvertera en delad postlåda tillbaka till en användare (privat) postlåda.

**Här är några riktigt viktiga saker som du behöver veta:**

- Användarpostlådan som du konverterar behöver en licens som tilldelats den innan du konverterar den till en delad postlåda. Annars visas inte alternativet för att konvertera postlådan. Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan. När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.

- Delade postlådor kan ha upp till 50 GB data utan att någon tilldelad licens. Om postlådan ska innehålla mer data än det behöver du tilldela en licens till den. Du kanske måste ta bort flera stora e-postmeddelanden (t.ex. sådana med bifogade filer) från den delade postlådan för att krympa dess storlek så att du kan ta bort licensen.

- Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).

- Reglerna är intakta när postlådan har konverterats till en delad postlåda.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Använda administrationscentret för Exchange för att konvertera en postlåda
 
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **mottagare postlådor** \> **Mailboxes**.

3. Markera användarpostlådan. Välj **Konvertera**under **Konvertera till delad postlåda**.

4. Om postlådan är mindre än 50 GB kan du ta bort [licensen från användaren](../manage/remove-licenses-from-users.md) och sluta betala för den. Ta inte bort användarens gamla postlåda. Den delade postlådan behöver ha den som en fästpunkt. Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre. Se [Ta bort en tidigare anställd från Office 365](../add-users/remove-former-employee.md).
    
5. För allt annat du behöver veta om delade postlådor, se [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>Använda administrationscentret för Microsoft 365 för att konvertera en postlåda

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Välj namnet på den användare vars postlåda du vill konvertera.

3. Återställ användarens lösenord.

> [!NOTE]
> Det krävs inte för att återställa användarens lösenord under postlådekonverteringen. Men om lösenordet inte återställs **fortsätter det ursprungliga användarnamnet och lösenordet att fungera** när postlådans konvertering är klar.

4. Välj Konvertera till delad postlåda under **Fler åtgärder**på fliken **E-post.** **Convert to shared mailbox** 

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera den användare vars postlåda du vill konvertera.

3. Expandera **E-postinställningar**i den högra rutan . Bredvid **Fler inställningar**väljer du Konvertera till delad **postlåda**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera den användare vars postlåda du vill konvertera.

3. Expandera **E-postinställningar**i den högra rutan . Bredvid **Fler inställningar**väljer du Konvertera till delad **postlåda**.

::: moniker-end


Om postlådan är mindre än 50 GB kan du [ta bort licensen från användaren](../manage/remove-licenses-from-users.md)och sluta betala för den. Ta inte bort användarens gamla postlåda. Den delade postlådan behöver ha den som en fästpunkt. Om du konverterar postlådan för en medarbetare som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre. Se [Ta bort en tidigare anställd från Office 365](../add-users/remove-former-employee.md).
    
För allt annat du behöver veta om delade postlådor, se [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda](create-a-shared-mailbox.md).


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Konvertera en borttagen användares postlåda

Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:

1. [Återställ användarens konto](../add-users/restore-user.md).

2. Kontrollera att en Office 365-licens har tilldelats till det.

3. Återställ användarens lösenord.
    
4. Vänta i 20-30 minuter på att postlådan återskapas.
    
5. Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.
    
6. När det är gjort kan du ta bort licensen från användarens postlåda. Ta inte bort användarens gamla postlåda. Den delade postlådan behöver ha den som en fästpunkt.
    
7. Lägg till medlemmar för den delade postlådan.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Konvertera en delad postlåda tillbaka till en användares (privata) postlåda

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
   
2. Välj **Delade mottagare** \> **.**

3. Markera den delade postlådan. Välj **Konvertera**under **Konvertera till vanlig postlåda**.

4. Gå tillbaka till administrationscentret. Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**. Tilldela en licens till kontot och återställ lösenordet.

   Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Konvertera en användares postlåda i en hybridmiljö

Om den här delade postlådan är i en hybridmiljö rekommenderar vi **starkt** (nästan kräver!) att du flyttar tillbaka användarpostlådan till lokal, konverterar användarpostlådan till en delad postlåda och flyttar sedan den delade postlådan tillbaka till molnet.

Här är varför: om du konverterar postlådan i molnet kan den konverteras, men lokalt tror fortfarande att postlådan är användarpostlådan, eftersom den nya verkligheten inte synkroniseras tillbaka till lokala.

Vanligtvis är detta inte ett problem, men det finns vissa scenarier där de lokala attributen (som tror att postlådan är användarenpostlådan) kan skriva över de nya molnversionerna av dessa attribut, och som ett resultat kan postlådan konvertera tillbaka. Detta är ett problem eftersom användarpostlådor kräver licenser **eller de är mjuka bort efter 30 dagar!**

Vi har tagit upp de flesta av anledningarna till att detta händer men det kan fortfarande hända, men sällan. Det är bäst att vara säker och flytta brevlådan tillbaka till lokala.

> [!NOTE]
> Om du är en del av organisationshantering eller mottagarhantering kan du använda skalet för Exchange Management för att ändra en användarpostlåda till en delad postlåda lokalt. Till exempel `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Se lösningen i den här supportlösningen till exempel när [delade postlådor oväntat konverteras till användarpostlådor](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)
  
## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
