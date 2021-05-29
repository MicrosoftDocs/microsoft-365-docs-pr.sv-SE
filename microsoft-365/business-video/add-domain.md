---
title: Lägga till en domän
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Din organisation kan behöva flera domäner så att kunderna kan hitta dig. Lär dig hur du lägger till en annan domän i din prenumeration.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706436"
---
# <a name="add-another-domain"></a>Lägga till en annan domän

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ditt företag kan behöva flera domännamn för olika ändamål. Du kanske till exempel vill lägga till en annan stavning av ditt företagsnamn eftersom kunderna redan använder det och deras meddelanden inte har nå dig.

## <a name="try-it"></a>Prova själv!

1. Välj Microsoft 365 i **administrationscentret.**
1. Under **Konfigurera din egen domän väljer** du **Visa**.
1. Välj **Manage** och sedan **Add domain**.
1. Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa**.
1. Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**
1. Logga in på din registrator om du uppmanas till det och välj sedan **Godkänn**.
1. Välj **Add the DNS records for me** och sedan **Next**.
1. Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som ska hanteras av en annan domän. Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna **för Skype för företag** och **Mobile Device Management för Office 365**.
1. Välj **Nästa,** **Godkänn** **, Nästa** och sedan **Slutför.** Din nya domän har lagts till.

Om du vill ta emot e-post på din nya domän måste du lägga till ett nytt e-postalias för varje användare:

1. Välj **Användare**, **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.
1. Välj **Hantera e-postalias** och sedan Lägg **till ett alias**.
1. Ange användarnamnet och välj sedan den nya domänen i listrutan.
1. Välj **Spara** ändringar och stäng sedan fönstret.
1. Upprepa de här stegen för alla användare som ska få e-post på den nya domänen.

## <a name="related-content"></a>Relaterat innehåll

[Lägga till en domän Microsoft 365](../admin/setup/add-domain.md) (artikel)\
[Lägg till DNS-poster för att ansluta din domän](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (artikel)\
[Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (artikel)\
[Domänens vanliga frågor och svar](../admin/setup/domains-faq.yml) (artikel)