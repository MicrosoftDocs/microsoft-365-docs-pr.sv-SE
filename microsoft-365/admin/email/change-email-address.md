---
title: Ändra din e-postadress så att en anpassad domän används
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: 'Ändra din första e-postadress till en vänlig e-postadress som tom@fourthcoffee.com. För att göra detta måste du köpa ett domännamn och lägga till det i Office 365. '
ms.openlocfilehash: 3e01f0bfb97fbef762fbd7162944ca25d882f142
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807732"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändra din e-postadress så att en anpassad domän används

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Den ursprungliga e-postadressen i Office 365 innehåller .onmicrosoft.com, t.ex. tom@fourthcoffee.onmicrosoft.com. Du kan ändra den till en enklare adress som tom@fourthcoffee.com. Du behöver först ditt eget domännamn, till exempel fourthcoffee.com. Om du redan har ett är det toppen! Om inte kan du ta reda på hur du [köper ett från en domänregistrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Din första e-postadress i Office 365 Tyskland innehåller onmicrosoft.de, till exempel tom@fourthcoffee.onmicrosoft.de. Du kan ändra den till en vänligare adress som tom@fourthcoffee.de. Du behöver ditt eget domännamn, som fourthcoffee.de först. Om du redan har en, bra! Om inte, kan du lära dig att [köpa en från en domän registrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Din första e-postadress i Office 365 som drivs av 21Vianet innehåller partner.onmschina.cn, till exempel tom@fourthcoffee.partner.onmschina.cn. Du kan ändra den till en vänligare adress som tom@fourthcoffee.cn. Du behöver ditt eget domännamn, som fourthcoffee.cn först. Om du redan har en, bra! Om inte, kan du lära dig att [köpa en från en domän registrator](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

När du ändrar din domäns e-post så att den kommer till Office 365, genom att uppdatera domänens MX-post vid konfigureringen, börjar ALL e-post som skickas till den domänen att komma till Office 365. Kontrollera att du har lagt till användare och skapat postlådor i Office 365 för alla som har e-posten på din domän INNAN du ändrar MX-posten. Vill du inte flytta e-posten för alla på domänen till Office 365? Då kan du göra så att [bara vissa e-postadresser använder Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändra din e-postadress för att använda din anpassade domän med hjälp av administrationscentret för Microsoft 365

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

2. Gå till sidan **Inställningar** > **domäner.** 

3. På sidan **Domäner** väljer du **Lägg till domän**.
    
4. Följ instruktionerna för att bekräfta att du äger domänen och för att ändra din e-postadress.
    
Du vägleds till rätt inställningar av domänen i Office 365.

> [!NOTE]
> Om du inte använder en Exchange-licens kan du inte använda domänen för att skicka eller ta emot e-postmeddelanden från Office 365-klienten.
  
## <a name="related-articles"></a>Relaterade artiklar

[Köpa en egen domän med Office 365](../get-help-with-domains/buy-a-domain-name.md)
 
