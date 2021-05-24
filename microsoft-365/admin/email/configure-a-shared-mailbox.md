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
description: Skapa en delad postlåda och konfigurera vissa inställningar för användarna, till exempel vidarebefordran av e-post och automatiska svar.
ms.openlocfilehash: c1d8007a2fcc45fbdd1a6943ee464e5aae8917b9
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635516"
---
# <a name="configure-shared-mailbox-settings"></a>Redigera inställningar för delad postlåda

När du har [skapat en delad](create-a-shared-mailbox.md)postlåda behöver du konfigurera vissa inställningar för postlådans användare, till exempel vidarebefordran av e-post och autosvar. Senare kanske du vill ändra andra inställningar, till exempel postlådenamn, medlemmar eller medlemsbehörigheter. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändra namn eller e-postalias för en delad postlåda eller ändra den primära e-postadressen

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan **Redigera** bredvid **Namn, E-post, E-postalias**.

3. Ange ett nytt namn eller lägg till ett annat alias. Om du vill ändra den primära e-postadressen måste postlådan ha flera e-postalias.

4. Välj **Spara**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Vidarebefordra e-postmeddelanden som skickas till en delad postlåda

Du behöver inte tilldela en licens till den delade postlådan för att vidarebefordra e-post som skickas till den. Du kan vidarebefordra meddelandena till en giltig e-postadress eller distributionslista.

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan Vidarebefordran av **e-post** \> **Redigera**.
    
3. Ställ in växlingsknappen på **På** och ange en e-postadress att vidarebefordra meddelandena till. Det kan vara vilken giltig e-postadress som helst. Om du vill vidarebefordra till flera adresser måste du skapa en [distributionsgrupp](/office365/admin/setup/create-distribution-lists) för adresserna och sedan ange namnet på gruppen i den här rutan.
    
4. Välj **Spara**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Skicka automatiska svar från en delad postlåda

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan **Redigera** \> **autosvar.**
    
3. Ändra växlingsknappen till **På** och välj om du vill skicka till personer inom eller utanför organisationen.

4. Skriv ett meddelande till personer inom organisation. Du endast lägga till text, inga bilder.

5. Om du även *vill* skicka ett svar till personer utanför organisationen markerar du kryssrutan, vem du vill ska få svaret och skriver texten. Det går inte bara att skicka till personer utanför organisationen, men inte till personer inom organisationen.

6. Välj **Spara**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Tillåta alla att se skickad e-post (svaren)

Standardinställningen är att e-post skickad från den delade postlådan inte sparas i den gemensamma Skickat-mappen. Den sparas istället hos den person som skickade meddelandet, i mappen Skickat.

Om du vill att alla ska kunna se skickade e-postmeddelanden redigerar du inställningarna för den delade postlådan i administrationscentret och **väljer Redigera skickade** \> **objekt.**


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Välj de appar som en delad postlåda kan använda för att komma åt e-post från Microsoft

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan **E-postprogram** \> **Redigera**.

3. Ställ in växlingsknappen **på På** för alla appar som du vill att medlemmarna ska kunna använda för att komma åt den delade postlådan. Ställ in växlingsknappen **på** Av för appar som du inte vill att de ska använda. 

4. Välj **Spara**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Sätta en delad postlåda i bevarande av juridiska skäl

Mer information om bevarande av juridiska skäl finns i [Skapa ett bevarande av juridiska skäl.](../../compliance/create-a-litigation-hold.md)

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan du vill redigera och välj sedan Bevarande av juridiska **skäl** \> **Redigera**.

3. Ställ in växlingsknappen på **På**. 

4. Alternativt kan du ange en varaktighet, en anteckning om kvart i kommentaren och en URL med mer information.  

5. Välj **Spara**.


## <a name="add-or-remove-members"></a>Lägga till eller ta bort medlemmar

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Välj den delade postlådan som du vill redigera och välj sedan **Medlemmar** \> **Redigera.**

3. Gör något av följande:
   - Om du vill lägga till medlemmar **väljer du Lägg till** medlemmar , söker efter eller väljer en medlem att lägga till och väljer sedan **Spara.**
   - Om du vill ta bort medlemmar använder du sökrutan för att söka efter medlemmen om det behövs, väljer **X** bredvid medlemmens namn och väljer sedan **Spara**. 

4. Välj **Spara** igen.

## <a name="add-or-remove-permissions-of-members"></a>Lägga till eller ta bort behörigheter för medlemmar

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan **Medlemmar** \> **Anpassa behörigheter.**

3. Välj **Redigera** bredvid den behörighet som du vill ändra för en medlem. 

4. Gör något av följande:
   - Om du vill ge behörighet till ytterligare en medlem väljer du **Lägg** till behörigheter , söker efter eller väljer en medlem att lägga till och väljer sedan **Spara**.
   - Om du vill ta bort behörigheten från en medlem använder du sökrutan för att söka efter medlemmen om det **behövs,** väljer **X** bredvid medlemmens namn och väljer sedan Spara . 

4. Välj **Spara** igen.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Visa eller dölja en delad postlåda i den globala adresslistan

Om du väljer att inte visa den delade postlådan i den globala adresslistan visas inte postlådan i organisationens adresslista, men den får fortfarande e-post som skickas till den. 

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

2. Markera den delade postlådan som du vill redigera och välj sedan **Visa i den globala adresslistan** \> **Redigera.**

3. Ställ in växlingsknappen på **På**  eller **Av**. 

4. Välj **Spara**.

> [!NOTE]
> Om du döljer en delad postlåda från adresslistan blir det omöjligt för nya medlemmar i delade postlådor att lägga till den dolda postlådan i sin Outlook-profil tills den delade postlådan visas igen i adresslistan. 

## <a name="related-content"></a>Relaterat innehåll

[Om delade postlådor](about-shared-mailboxes.md) (artikel)\
[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)\
[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)\
[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)