---
title: Konfigurera vidarebefordran av e-post
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med Office365.
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780259"
---
# <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Som administratör för en organisation kan du ha företagskrav för att konfigurera vidarebefordran av e-post för en användares postlåda. Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.

  
## <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

 Innan du konfigurerar vidarebefordran av e-post bör du tänka på följande: 

- När du har konfigurerat vidarebefordran av e-post kommer endast **nya** e-postmeddelanden som skickas till *från* postlådan att vidarebefordras. 
    
- Vidarebefordran av e-post kräver att *från-kontot* har en licens. Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md). På det sättet kan flera personer komma åt den. En delad postlåda kan dock inte vara större än 50 GB. 
    
Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att kunna göra så här. Mer information finns i avsnittet [Om administratörsroller](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan. 
 
3. Välj **Hantera vidarebefordran av e-post**på fliken **E-post** . 
  
4. På sidan vidarebefordran av e-post väljer du **Vidarebefordra alla e-postmeddelanden som skickas till den här postlådan,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara ändringar**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna. Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i den och ställ sedan in vidarebefordran så att den pekar på DL med hjälp av instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post till dig eller tar bort deras licens!  Om du gör det kommer vidarebefordran av e-post att upphöra. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>. 
    
2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan. 

3. Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .

4. På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna. Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i den och ställ sedan in vidarebefordran så att den pekar på DL med hjälp av instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post till dig eller tar bort deras licens!  Om du gör det kommer vidarebefordran av e-post att upphöra.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 
    
2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan. 

3. Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **Vidarebefordra e-post** .

4. På sidan vidarebefordran av e-post ställer du in växlingsknappen **på ,** anger vidarebefordringsadressen och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att ställa in en regel i Outlook för att vidarebefordra till adresserna. Mer information finns i [Använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Eller skapa [en distributionsgrupp](../setup/create-distribution-lists.md)i administrationscentret, [lägga till adresserna](add-user-or-contact-to-distribution-list.md)i den och ställ sedan in vidarebefordran så att den pekar på DL med hjälp av instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post till dig eller tar bort deras licens!  Om du gör det kommer vidarebefordran av e-post att upphöra. 

::: moniker-end 
