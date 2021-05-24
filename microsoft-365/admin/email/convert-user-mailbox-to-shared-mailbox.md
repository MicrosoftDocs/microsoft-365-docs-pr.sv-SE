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
description: 'Lär dig hur du konverterar en privat postlåda till en delad postlåda som flera personer kan komma åt istället för bara en person. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635480"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Konvertera en användarpostlåda till en delad postlåda

När du konverterar en användares postlåda till en delad postlåda sparas alla befintliga e-postmeddelanden och den befintliga kalendern. Enda skillnaden är att informationen nu finns i en delad postlåda där flera personer får tillgång till den istället för en enda person. Du kan senare konvertera en delad postlåda tillbaka till en användarpostlåda (privat).

## <a name="before-you-begin"></a>Innan du börjar

**Här är några mycket viktiga saker som du behöver veta:**

- Den användarpostlåda du konverterar måste ha en tilldelad licens innan du konverterar postlådan till en delad postlåda. Annars visas inte alternativet för att konvertera postlådan. Om du har tagit bort licensen lägger du till den igen så att du kan konvertera postlådan. När du har konverterat postlådan till en delad postlåda kan du ta bort licensen från användarens konto.

- Delade postlådor kan ha upp till 50 GB data utan att någon tilldelad licens. Om du vill lagra mer data än det behöver du tilldela en licens till den. Du kan behöva ta bort flera stora e-postmeddelanden (t.ex. sådana med bifogade filer) från den delade postlådan för att krympa den så att du kan ta bort licensen.

- Ta inte bort den gamla användarens konto. Det krävs för att fästa den delade postlådan. Om du redan har tagit bort användarkontot läser du [Konvertera en borttagen användares postlåda](#convert-the-mailbox-of-a-deleted-user).

- Reglerna är intakta när postlådan har konverterats till en delad postlåda.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Använda administrationscentret Exchange för att konvertera en postlåda
 
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj  \> **Mottagare, postlådor**.

3. Markera användarens postlåda. Under **Konvertera till delad postlåda** väljer du **Konvertera**.

4. Om postlådan är mindre än 50 GB kan du ta bort licensen från [användaren](../manage/remove-licenses-from-users.md)och sluta betala för den. Ta inte bort användarens konto. Den delade postlådan behöver ha den som en fästpunkt. Om du konverterar postlådan för en anställd som lämnar organisationen bör du vidta ytterligare åtgärder för att se till att de inte kan logga in längre. Se Ta [bort en tidigare anställd från Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Det är inte obligatoriskt att återställa användarens lösenord vid postlådekonvertering. Om lösenordet inte återställs fortsätter det ursprungliga **användarnamnet och lösenordet att fungera** när postlådekonverteringen är klar.

Allt annat du behöver veta om delade postlådor finns i [Om delade postlådor](about-shared-mailboxes.md) och [Skapa en delad postlåda.](create-a-shared-mailbox.md)

> [!NOTE]
> Delade postlådor kräver inte en separat licens. Om du däremot vill aktivera In-Place-arkiv eller placera en licens för In-Place-bevarande eller bevarande av juridiska skäl för en delad postlåda måste du tilldela en licens för Exchange Online-abonnemang 1 med Exchange Online - arkivering eller Exchange Online abonnemang 2 till postlådan.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Konvertera en borttagen användares postlåda

Anta att du har tagit bort ett användarkonto och du nu vill konvertera användarens gamla postlåda till en delad postlåda. Det här behöver du göra:

1. [Återställa användarens konto.](../add-users/restore-user.md)

2. Kontrollera att Microsoft 365 licens är tilldelad till den.

3. Återställ användarens lösenord.
    
4. Vänta i 20-30 minuter på att postlådan återskapas.
    
5. Sedan följer du instruktionerna på sidan om du vill konvertera postlådan till en delad postlåda.
    
6. När det är klart kan du ta bort licensen från användarens postlåda. Ta inte bort användarens gamla postlåda. Den delade postlådan behöver ha den som en fästpunkt.
    
7. Lägg till medlemmar för den delade postlådan.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Konvertera en delad postlåda tillbaka till en användares (privata) postlåda

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
   
2. Välj **Mottagare som** \> **delas**.

3. Välj den delade postlådan. Under **Konvertera till vanlig postlåda** väljer du **Konvertera**.

4. Gå tillbaka till administrationscentret. Välj användarkontot som är kopplat till den gamla delade postlådan under **Användare**. Tilldela en licens till kontot och återställ lösenordet.

   Det tar några minuter innan postlådan har konfigurerats, men sedan kan personen som kommer att använda det kontot börja göra det. När användaren loggar in ser han/hon e-postmeddelanden och kalenderobjekt som brukade finnas i den delade postlådan.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Konvertera en användares postlåda i en hybridmiljö

Mer information om hur du konverterar en användarpostlåda till en delad postlåda i Exchange hybridmiljö finns i:

 - [Cmdlets för att skapa eller ändra en fjärransluten delad postlåda i en Exchange miljö](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Delade postlådor konverteras oväntat till användarpostlådor när katalogsynkroniseringen har Exchange i en hybriddistribution](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Om du är medlem i rollgruppen Organisationshantering eller Mottagarhantering kan du använda Exchange Management Shell för att ändra en användarpostlåda till en delad postlåda lokalt. Till exempel `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Relaterat innehåll

[Om delade postlådor](about-shared-mailboxes.md) (artikel)\
[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)\
[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)\
[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)\
[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)