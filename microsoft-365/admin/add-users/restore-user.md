---
title: Återställa en användare
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Inom 30 dagar efter att du tagit bort ett användarkonto kan du återställa kontot och alla data och användaren kan logga in med samma konto.
ms.openlocfilehash: f849fe8e403aa9a72eccb4dd65665ec9f33618d1
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779656"
---
# <a name="restore-a-user"></a>Återställa en användare
   
Om du återställer ett användarkonto inom 30 dagar från det att det togs bort, återställs kontot och alla associerade data. Användaren kan logga in med samma arbets- eller skolkonto. Postlådan återställs i sin helhet. Om du vill ta reda på hur mycket tid som återstår innan ett visst användarkonto inte längre kan återställas [kontaktar du oss](../../business-video/get-help-support.md).
  
Här är några tips:
  
- Se till att det finns tillgängliga licenser att tilldela kontot.
    
- Om ditt företag använder Active Directory, finns information om hur du återställer ett användarkonto i Felsöka borttagna användarkonton [i Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts). 
    
## <a name="restore-one-or-more-user-accounts"></a>Återställa ett eller flera användarkonton

Du måste vara global Microsoft 365 administratör eller användarhanteringsadministratör för att kunna göra det här. 

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.

2. På sidan **Borttagna användare** markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
3. Följ anvisningarna för att ange deras lösenord och välj sedan **Återställ**.
    
4. Om användaren återställs väljer du Skicka **e-post och stäng**. Om det uppstår en namnkonflikt eller en proxyadresskonflikt kan du läsa instruktionerna nedan om återställning av dessa konton.
    
När du har återställt en användare bör du meddela dem att deras lösenord har ändrats och följa upp med dem.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Återställa en användare som har en användarnamnskonflikt

En användarnamnskonflikt inträffar när du tar bort ett användarkonto, skapar ett nytt användarkonto med samma användarnamn (antingen för samma användare eller för en annan användare med ett liknande namn) och sedan försöker återställa det borttagna kontot.
  
Om du vill lösa detta ersätter du det aktiva användarkontot med det konto som du återställer. Eller tilldela det konto som du återställer ett annat användarnamn, så att inte båda kontona har samma användarnamn. Följ nedanstående anvisningar.

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.
  
2. På **sidan Borttagna** användare markerar du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
    > [!NOTE]
    > Om återställandet av två eller fler användare misslyckas visas ett felmeddelande som informerar dig om att återställningsåtgärden misslyckades för vissa användare. Ta fram loggen och kontrollera vilka användare som inte återställdes. Dessa konton måste du återställa ett åt gången. 
  
3. Följ anvisningarna för att ange lösenordet och välj **Återställ**.
    
4. Ett meddelande dyker upp där det står att det inte gick att återställa kontot. Gör något av följande:
    
  - Avbryt återställningen och byt namn på den aktiva användaren. Försök sedan återställa igen.
    
  - ELLER, skriv en ny primär e-postadress för användaren och välj **Återställ**.
    
5. Granska resultaten och välj sedan **Stäng**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Återställa en användare som har en proxyadresskonflikt

En proxyadresskonflikt inträffar när du tar bort ett användarkonto som innehåller en proxyadress, tilldelar ett annat konto samma proxyadress och sedan försöker återställa det borttagna kontot. Så här löser du problemet:
  
Du måste ha [administratörsbehörighet](about-admin-roles.md) i Microsoft 365 göra detta. 

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Användare borttagna</a> användare.

2. Markera användaren som ska återställas på sidan **Borttagna användare** och välj sedan **Återställ**. 
    
3. På sidan **Återställ** följer du anvisningarna för att ange lösenordet och väljer **Återställ**. Proxyadresser med konflikter tas automatiskt bort från användaren som du återställer.
    
4. Granska resultaten och välj sedan **Stäng**.

## <a name="related-content"></a>Relaterat innehåll

[Ta bort en användare](delete-a-user.md) (artikel)\
[Tilldela administratörsroller](assign-admin-roles.md) (video)\
[Tilldela användare licenser](../manage/assign-licenses-to-users.md) (artikel)
