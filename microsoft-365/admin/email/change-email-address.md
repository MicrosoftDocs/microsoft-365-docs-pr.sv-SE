---
title: Ändra din e-postadress så att en anpassad domän används
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Ändra din initiala e-postadress till en egen e-postadress som tom@fourthcoffee.com. För att göra detta måste du köpa ett domän namn och lägga till det i Microsoft 365. '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814486"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändra din e-postadress så att en anpassad domän används

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Din initiala e-postadress i Microsoft 365 inkluderar. onmicrosoft.com, till exempel tom@fourthcoffee.onmicrosoft.com. Du kan ändra till en användarvänlig adress som tom@fourthcoffee.com. Du behöver ditt eget domän namn, till exempel fourthcoffee.com först. Om du redan har en, bra! Om inte, kan du lära dig hur du [köper en från en domän registrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Din initiala e-postadress i Office 365 Germany innehåller. onmicrosoft.de, till exempel tom@fourthcoffee.onmicrosoft.de. Du kan ändra till en användarvänlig adress som tom@fourthcoffee.de. Du behöver ditt eget domän namn, till exempel fourthcoffee.de först. Om du redan har en, bra! Om inte, kan du lära dig hur du [köper en från en domän registrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Din initiala e-postadress i Office 365 som drivs av 21Vianet innehåller partner.onmschina.cn, till exempel tom@fourthcoffee.partner.onmschina.cn. Du kan ändra till en användarvänlig adress som tom@fourthcoffee.cn. Du behöver ditt eget domän namn, till exempel fourthcoffee.cn först. Om du redan har en, bra! Om inte, kan du lära dig hur du [köper en från en domän registrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

När du ändrar din domäns e-post till Microsoft 365 genom att uppdatera din domäns MX-post under installationen kommer ALL e-post som skickas till domänen att komma till Microsoft 365. Kontrol lera att du har lagt till användare och skapat post lådor i Microsoft 365 för alla som har e-post på din domän innan du ändrar MX-posten. Vill du inte flytta e-post för alla i domänen till Microsoft 365? Du kan vidta åtgärder för att [pilot för Microsoft 365 med bara några få e-postadresser](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändra din e-postadress så att den använder din anpassade domän med administrations centret för Microsoft 365

Du måste ha ett globalt administratörs konto för att kunna utföra de här stegen. 

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrations centret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Gå till sidan **konfigurations**  >  **domäner** . 

3. På sidan **Domains** väljer du **Lägg till domän**.
    
4. Följ instruktionerna för att bekräfta att du äger domänen och för att ändra din e-postadress.
    
Du lär dig att få allting konfigurerat korrekt med din domän i Microsoft 365.

> [!NOTE]
> Om du inte använder en Exchange-licens kan du inte använda domänen för att skicka eller ta emot e-post från Microsoft 365-klienten.
  
## <a name="related-articles"></a>Relaterade artiklar

[Köpa en egen domän med hjälp av Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
