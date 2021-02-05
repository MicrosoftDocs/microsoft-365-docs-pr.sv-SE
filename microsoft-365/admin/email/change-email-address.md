---
title: Ändra din e-postadress så att en anpassad domän används
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Ändra den ursprungliga e-postadressen till en egen e-postadress som tom@fourthcoffee.com. Om du vill göra det måste du köpa ett domännamn och lägga till det i Microsoft 365. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114027"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändra din e-postadress så att en anpassad domän används

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Din ursprungliga e-postadress i Microsoft 365 innehåller .onmicrosoft.com, till exempel tom@fourthcoffee.onmicrosoft.com. Du kan ändra den till en mer användarvänlig adress som tom@fourthcoffee.com. Du behöver ditt eget domännamn, till exempel fourthcoffee.com först. Om du redan har ett, bra! Annars kan du ta reda på hur du [köper en från en domänregistrator.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

::: moniker range="o365-germany"

Din ursprungliga e-postadress i Office 365 Germany innehåller .onmicrosoft.de, till exempel tom@fourthcoffee.onmicrosoft.de. Du kan ändra den till en mer användarvänlig adress som tom@fourthcoffee.de. Du behöver ditt eget domännamn, till exempel fourthcoffee.de först. Om du redan har ett, bra! Annars kan du ta reda på hur du [köper en från en domänregistrator.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

::: moniker range="o365-21vianet"

Din ursprungliga e-postadress i Office 365 som drivs av 21Vianet innehåller partner.onmschina.cn, till exempel tom@fourthcoffee.partner.onmschina.cn. Du kan ändra den till en mer användarvänlig adress som tom@fourthcoffee.cn. Du behöver ditt eget domännamn, till exempel fourthcoffee.cn först. Om du redan har ett, bra! Annars kan du ta reda på hur du [köper en från en domänregistrator.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

När du ändrar e-posten för din domän så att den ska gå till Microsoft 365 genom att uppdatera domänens MX-post vid konfigurationen börjar ALL e-post som skickas till den domänen gå till Microsoft 365. Kontrollera att du har lagt till användare och skapat postlådor i Microsoft 365 för alla som har e-post i din domän INNAN du ändrar MX-posten. Vill du inte flytta e-posten för alla i din domän till Microsoft 365? I stället kan du vidta åtgärder [för att pilottesta Microsoft 365 med bara några få e-postadresser.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändra din e-postadress så att den använder din egen domän i administrationscentret för Microsoft 365

Du måste ha ett globalt administratörskonto för att utföra de här stegen. 

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>på . 

::: moniker-end 

2. Gå till **sidan**  >  **Konfigurationsdomäner.** 

3. På sidan **Domains** väljer du **Lägg till domän**.
    
4. Följ instruktionerna för att bekräfta att du äger domänen och för att ändra din e-postadress.
    
Du vägleds så att allt konfigureras korrekt med din domän i Microsoft 365.

> [!NOTE]
> Om du inte använder en Exchange-licens kan du inte använda domänen för att skicka eller ta emot e-postmeddelanden från Microsoft 365-klienten.
  
## <a name="related-articles"></a>Relaterade artiklar

[Köpa en egen domän med Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
