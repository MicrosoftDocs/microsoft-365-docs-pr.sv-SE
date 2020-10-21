---
title: Konfigurera vidarebefordran av e-post
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med Office365.
ms.openlocfilehash: d19e2c533be6fac927bdf2aa65d72acab9fad6f6
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645533"
---
# <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Som administratör för en organisation kan du ha företags krav för att konfigurera e-postvidarekoppling för en användares post låda. Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.

  
## <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

 Observera följande innan du konfigurerar e-postvidarebefordran: 

- När du har konfigurerat e-postvidarebefordran blir bara **nya** e-postmeddelanden som skickas till  *från*  -post lådan vidare. 
    
- För e-postvidarekoppling krävs det att  *from*  -kontot har en licens. Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md). På det sättet kan flera personer komma åt den. En delad postlåda kan dock inte vara större än 50 GB. 
    
Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att utföra de här stegen. Mer information finns i avsnittet [om administratörs roller](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan. 
 
3. Välj **Hantera e-postvidarebefordran**på fliken **e-post** . 
  
4. På sidan e-postchatt väljer du **vidarebefordra alla e-postmeddelanden som skickas till den här post lådan**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara ändringar**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>. 
    
2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan. 

3. Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **e-postvidarebefordran** .

4. På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 
    
2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan. 

3. Expandera **e-postinställningar**och välj sedan **Redigera**i avsnittet **e-postvidarebefordran** .

4. På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.
    
    **Om du vill vidarebefordra till flera e-postadresser**kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.
    
5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling. 

::: moniker-end 
