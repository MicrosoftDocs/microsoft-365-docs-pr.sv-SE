---
title: Återställa en användare i Office 365
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Lär dig hur du återställer borttagna Office 365-användarkonton och alla associerade data.
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808681"
---
# <a name="restore-a-user-in-office-365"></a>Återställa en användare i Office 365
   
Om du återställer ett användarkonto inom 30 dagar från det att det togs bort, återställs kontot och alla associerade data. Användaren kan logga in med samma arbets- eller skolkonto. Postlådan återställs i sin helhet. Om du vill ta reda på hur mycket tid som återstår innan ett visst användarkonto inte längre kan återställas [kontaktar du oss](../contact-support-for-business-products.md).
  
Här är några tips:
  
- Se till att det finns tillgängliga Office 365-licenser som du kan tilldela kontot.
    
- Om ditt företag använder Active Directory, se [Felsökning av borttagna konton i Office 365](https://support.microsoft.com/kb/2619308) för instruktioner om återställning av användarkonton. 
    
## <a name="restore-one-or-more-user-accounts"></a>Återställa ett eller flera användarkonton

Du måste vara global administratör eller användarhanteringsadministratör i Office 365 för att kunna göra så här. 
  
 
::: moniker range="o365-worldwide"

1. Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

2. På sidan **Borttagna användare** väljer du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
 
3. Följ anvisningarna för att ange deras lösenord och välj sedan **Återställ**.
    
4. Om användaren har återställts väljer du **Skicka e-post och stäng**. Om det uppstår en namnkonflikt eller en proxyadresskonflikt kan du läsa instruktionerna nedan om återställning av dessa konton.
    
När du har återställt en användare kontrollerar du att du meddelar dem att deras lösenord har ändrats och att du följer upp med dem.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Återställa en användare som har en användarnamnskonflikt
<a name="RestoreUserNameConflict"> </a>

En användarnamnskonflikt inträffar när du tar bort ett användarkonto, skapar ett nytt användarkonto med samma användarnamn (antingen för samma användare eller för en annan användare med ett liknande namn) och sedan försöker återställa det borttagna kontot.
  
Om du vill lösa detta ersätter du det aktiva användarkontot med det konto som du återställer. Eller tilldela det konto som du återställer ett annat användarnamn, så att inte båda kontona har samma användarnamn. Följ nedanstående anvisningar.
  

::: moniker range="o365-worldwide"

1. Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

  
2. På sidan **Borttagna användare** markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
    > [!NOTE]
    > Om återställandet av två eller fler användare misslyckas visas ett felmeddelande som informerar dig om att återställningsåtgärden misslyckades för vissa användare. Ta fram loggen och kontrollera vilka användare som inte återställdes. Dessa konton måste du återställa ett åt gången. 
  
3. Följ anvisningarna för att ange lösenordet och välj **Återställ**.
    
4. Ett meddelande dyker upp där det står att det inte gick att återställa kontot. Gör något av följande:
    
  - Avbryt återställningen och byt namn på den aktiva användaren. Försök sedan återställa igen.
    
  - ELLER skriver du en ny primär e-postadress för användaren och väljer **Återställ**.
    
5. Granska resultaten och välj sedan **Stäng**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Återställa en användare som har en proxyadresskonflikt

En proxyadresskonflikt inträffar när du tar bort ett användarkonto som innehåller en proxyadress, tilldelar ett annat konto samma proxyadress och sedan försöker återställa det borttagna kontot. Så här löser du problemet:
  
Du måste ha [administratörsbehörigheter](about-admin-roles.md) i Office 365 för att göra detta. 
  

::: moniker range="o365-worldwide"

1. Gå till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna användare</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj sedan **Användare** \> **borttagna användare**.

::: moniker-end

2. Markera användaren som ska återställas på sidan **Borttagna användare** och välj sedan **Återställ**. 
    
3. På sidan **Återställ** följer du instruktionerna för att ange lösenordet och väljer **Återställ**. Proxyadresser med konflikter tas automatiskt bort från användaren som du återställer.
    
4. Granska resultaten och välj sedan **Stäng**.

## <a name="related-articles"></a>Relaterade artiklar

[Ta bort en användare](delete-a-user.md)
  

