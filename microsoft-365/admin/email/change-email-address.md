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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Ändra din första e-postadress till en vänlig e-postadress som tom@fourthcoffee.com. För att göra detta måste du köpa ett domännamn och lägga till det i Microsoft 365. '
ms.openlocfilehash: 50739c01fda9528140870798324dd69a1c68abce
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140506"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändra din e-postadress så att en anpassad domän används

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Din första e-postadress i Microsoft 365 innehåller .onmicrosoft.com, till exempel tom@fourthcoffee.onmicrosoft.com. Du kan ändra den till en vänligare adress som tom@fourthcoffee.com. Du behöver ditt eget domännamn, som fourthcoffee.com först. Om du redan har en, bra! Om inte, kan du lära dig att [köpa en från en domänregistratorer](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Din första e-postadress i Office 365 Tyskland innehåller .onmicrosoft.de, till exempel tom@fourthcoffee.onmicrosoft.de. Du kan ändra den till en vänligare adress som tom@fourthcoffee.de. Du behöver ditt eget domännamn, som fourthcoffee.de först. Om du redan har en, bra! Om inte, kan du lära dig att [köpa en från en domänregistratorer](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Din första e-postadress i Office 365 som drivs av 21Vianet innehåller partner.onmschina.cn, till exempel tom@fourthcoffee.partner.onmschina.cn. Du kan ändra den till en vänligare adress som tom@fourthcoffee.cn. Du behöver ditt eget domännamn, som fourthcoffee.cn först. Om du redan har en, bra! Om inte, kan du lära dig att [köpa en från en domänregistratorer](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

När du ändrar domänens e-post så att den kommer till Microsoft 365, genom att uppdatera domänens MX-post under installationen, kommer alla e-postmeddelanden som skickas till den domänen att börja komma till Microsoft 365. Kontrollera att du har lagt till användare och skapat postlådor i Microsoft 365 för alla som har e-post på din domän innan du ändrar MX-posten. Vill du inte flytta e-post för alla på domänen till Microsoft 365? Du kan vidta åtgärder för att [testa Microsoft 365 med bara några e-postadresser istället](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändra din e-postadress så att den använder din anpassade domän med hjälp av administrationscentret för Microsoft 365

Du måste ha ett globalt administratörskonto för att kunna utföra dessa steg. 

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Gå till sidan > **Installationsdomäner.** **Setup** 

3. På sidan **Domäner** väljer du **Lägg till domän**.
    
4. Följ instruktionerna för att bekräfta att du äger domänen och för att ändra din e-postadress.
    
Du får hjälp om du vill att allt ska konfigureras korrekt med domänen i Microsoft 365.

> [!NOTE]
> Om du inte använder en Exchange-licens kan du inte använda domänen för att skicka eller ta emot e-postmeddelanden från Microsoft 365-klientinnehavaren.
  
## <a name="related-articles"></a>Relaterade artiklar

[Köpa en anpassad domän med Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
