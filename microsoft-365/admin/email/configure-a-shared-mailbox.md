---
title: Konfigurera en delad postlåda
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: När du har skapat en delad postlåda vill du konfigurera vissa inställningar för användarna, till exempel vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamnet eller medlemmarna.
ms.openlocfilehash: edea829a8578387459afe3ce4889dfa620f95956
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807224"
---
# <a name="configure-a-shared-mailbox"></a>Konfigurera en delad postlåda

När du har [skapat en delad postlåda](create-a-shared-mailbox.md)vill du konfigurera vissa inställningar för postlådeanvändarna, till exempel vidarebefordran av e-post och automatiska svar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamn, medlemmar eller medlemsbehörigheter. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändra namn eller e-postalias för en delad postlåda eller ändra den primära e-postadressen

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Redigera bredvid** **Namn, E-post, E-postalias**.

3. Ange ett nytt namn eller lägg till ett annat alias. Om du vill ändra den primära e-postadressen måste postlådan ha mer än ett e-postalias.

4. Välj **Spara**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Vidarebefordra e-postmeddelanden som skickas till en delad postlåda

Du behöver inte tilldela en licens till den delade postlådan för att vidarebefordra e-post som skickas till den. Du kan vidarebefordra meddelandena till en giltig e-postadress eller distributionslista.

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Redigera e-post.** \> **Edit**
    
3. Ställ in växlingen **på På**och ange en e-postadress för att vidarebefordra meddelandena till. Det kan vara vilken giltig e-postadress som helst. Om du vill vidarebefordra till flera adresser måste du [skapa en distributionsgrupp](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) för adresserna och sedan ange namnet på gruppen i den här rutan.
    
4. Välj **Spara**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Skicka automatiska svar från en delad postlåda

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Redigera** **Automatiska svar** \> .
    
3. Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.

4. Skriv ett meddelande till personer inom organisation. Du endast lägga till text, inga bilder.

5. Om du *också* vill skicka ett svar till personer utanför organisationen markerar du kryssrutan, vem du vill få svaret och skriver texten. Det finns inget sätt att bara skicka till personer utanför organisationen, men inte till personer inom organisationen.

6. Välj **Spara**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Tillåta alla att se skickad e-post (svaren)

Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.

Om du vill tillåta alla att se e-postmeddelandet Skickat redigerar du inställningarna för delade postlådeinställningar i administrationscentret och väljer **Redigera** **skickade objekt** \> .


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a>Välj de appar som en delad postlåda kan använda för att komma åt Office 365-e-post

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Redigera e-postappar** \> **.**

3. Ställ in växlingen **på På** för alla appar som du vill att medlemmarna ska kunna använda för att komma åt den delade postlådan. Ställ in växlingen på **Av** för alla appar som du inte vill att de ska använda. 

4. Välj **Spara**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Spärra en delad postlåda vid spärr

Mer information om spärrning av rättstvister finns i [Skapa en rättstvistsspärr](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Spärra** \> **Redigera.**

3. Ställ in växlingsknappen **på På**. 

4. Du kan också ange en varaktighet, s anmärkning om spärren och en WEBBADRESS med mer information.  

5. Välj **Spara**.


## <a name="add-or-remove-members"></a>Lägga till eller ta bort medlemmar

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Medlemmar** \> **Redigera**.

3. Välj ett av följande alternativ:
   - Om du vill lägga till medlemmar väljer du **Lägg till medlemmar,** söker efter eller väljer en medlem som ska läggas till och väljer sedan **Spara**.
   - Om du vill ta bort medlemmar använder du sökrutan för att söka efter medlemmen om det behövs, markera **X** bredvid medlemmens namn och välj sedan **Spara**. 

4. Välj **Spara** igen.

## <a name="add-or-remove-permissions-of-members"></a>Lägga till eller ta bort behörigheter för medlemmar

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Behörigheter För medlemmar** \> **Anpassa**.

3. Välj **Redigera bredvid** den behörighet som du vill ändra för en medlem. 

4. Välj ett av följande alternativ:
   - Om du vill ge den behörigheten till ytterligare en medlem väljer du **Lägg till behörigheter,** söker efter eller väljer en medlem som ska läggas till och väljer sedan **Spara**.
   - Om du vill ta bort behörigheten från en medlem använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer sedan **Spara**. 

4. Välj **Spara** igen.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Visa eller dölja en delad postlåda i den globala adresslistan

Om du väljer att inte visa den delade postlådan i den globala adresslistan visas inte postlådan i organisationens adresslista, men den får fortfarande e-post som skickas till den. 

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">administrationscentret.</a>

::: moniker-end 

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > delade postlådor i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> **Shared mailboxes** 

::: moniker-end

2. Markera den delade postlåda som du vill redigera och välj sedan **Visa i den globala adresslistan** \> **Redigera**.

3. Ställ in växlingsknappen **på På** eller **Av**. 

4. Välj **Spara**.

> [!NOTE]
> Om du döljer en delad postlåda från adresslistan blir det omöjligt för nya medlemmar i delade postlådefiler att lägga till den dolda postlådan i sin Outlook-profil tills den delade postlådan visas igen i adresslistan. 

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
