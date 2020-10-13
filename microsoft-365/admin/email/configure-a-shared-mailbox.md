---
title: Redigera inställningar för delad postlåda
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: När du har skapat en delad post låda ska du konfigurera vissa inställningar för dess användare, till exempel vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel post lådans namn eller medlemmar.
ms.openlocfilehash: a007b3ca810bdfc00176e71a737a510230f18113
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445681"
---
# <a name="configure-shared-mailbox-settings"></a>Redigera inställningar för delad postlåda

När du har [skapat en delad post låda](create-a-shared-mailbox.md)kan du konfigurera vissa inställningar för användare av post lådor, till exempel vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel namn på post låda, medlemmar eller medlem. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändra namn eller e-postalias för en delad post låda eller ändra den primära e-postadressen

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **redigera** bredvid **namn, e-post, e-postalias**.

3. Ange ett nytt namn eller Lägg till ett annat alias. Om du vill ändra den primära e-postadressen måste din post låda ha fler än ett e-postalias.

4. Välj **Spara**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Vidarebefordra e-postmeddelanden som skickas till en delad postlåda

Du behöver inte tilldela en licens till den delade post lådan för att vidarebefordra e-post som skickas till den. Du kan vidarebefordra meddelanden till alla giltiga e-postadresser och distributions listor.

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan redigera **e-postvidarekoppling** \> **Edit**.
    
3. Ställ in växlings knappen **på på**och ange en e-postadress för att vidarebefordra meddelanden till. Det kan vara en valfri giltig e-postadress. Om du vill vidarebefordra till flera adresser måste du [skapa en distributions grupp](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) för adresserna och sedan ange namnet på gruppen i den här rutan.
    
4. Välj **Spara**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Skicka automatiska svar från en delad postlåda

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **autosvar** \> **Edit**.
    
3. Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.

4. Skriv ett meddelande till personer inom organisation. Du endast lägga till text, inga bilder.

5. Om du *även* vill skicka ett svar till personer utanför organisationen markerar du kryss rutan som du vill ska få svaret från och skriver texten. Det går inte att bara skicka till personer utanför organisationen, men inte till personer inom organisationen.

6. Välj **Spara**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Tillåta alla att se skickad e-post (svaren)

Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.

Om du vill att alla ska kunna se det skickade e-postmeddelandet redigerar du inställningarna för delade post lådor i administrations **Sent items** centret och väljer \> **Redigera**skickat.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Välj de program som en delad post låda kan använda för att komma åt Microsoft-e-post

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan redigera **e-postprogram** \> **Edit**.

3. Ställ in växlings knappen **på** för alla program som du vill att medlemmar ska kunna använda för att komma åt den delade post lådan. Ställ in växlings knappen på **av** för de program som du inte vill att de ska använda. 

4. Välj **Spara**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Lägga till en delad post låda i en tvist

Om du vill veta mer om rättsliga undantag läser du [skapa en tvist](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **rättsliga spärr** \> **redigering**.

3. Ställ in växlings knappen **på på**. 

4. Du kan också ange en varaktighet, anteckningen för spärren och en URL-adress med mer information.  

5. Välj **Spara**.


## <a name="add-or-remove-members"></a>Lägga till eller ta bort medlemmar

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **medlemmar** \> **Edit**.

3. Gör något av följande:
   - Om du vill lägga till medlemmar väljer du **Lägg till medlemmar**, Sök efter eller markera en medlem som du vill lägga till och väljer sedan **Spara**.
   - För att ta bort medlemmar, Använd sökrutan för att söka efter medlemmen om det behövs, Välj **X** bredvid medlemmens namn och välj sedan **Spara**. 

4. Välj **Spara** igen.

## <a name="add-or-remove-permissions-of-members"></a>Lägga till eller ta bort medlemmars behörigheter

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **medlemmar** , \> **Anpassa behörigheter**.

3. Välj **Redigera** bredvid den behörighet du vill ändra för en medlem. 

4. Gör något av följande:
   - Om du vill ge den behörigheten till en medlem väljer du **Lägg till behörigheter**, söker efter eller väljer en medlem som du vill lägga till och väljer sedan **Spara**.
   - Om du vill ta bort tillstånd från en medlem kan du använda sökrutan för att söka efter medlemmen, om det behövs, välja **X** bredvid medlemmens namn och sedan **Spara**. 

4. Välj **Spara** igen.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Visa eller dölja en delad post låda i den globala adress listan

Om du väljer att inte visa den delade post lådan i den globala adress listan visas inte post lådan i organisationens adress lista, men e-post skickas till den. 

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end 

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Grupper** > **Delade postlådor**. 

::: moniker-end

2. Markera den delade post låda som du vill redigera och välj sedan **Visa i global adress lista** \> **redigering**.

3. Ställ in växlings knappen **på**  eller **av**. 

4. Välj **Spara**.

> [!NOTE]
> Om du döljer en delad post låda från adress listan blir det omöjligt för nya delade post lådor att lägga till den dolda post lådan i sin Outlook-profil förrän den delade post lådan visas i adress listan. 

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
