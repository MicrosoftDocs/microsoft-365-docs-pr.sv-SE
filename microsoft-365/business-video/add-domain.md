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
description: Lär dig hur du lägger till en annan domän i din prenumeration.
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903748"
---
# <a name="add-another-domain"></a>Lägga till en annan domän

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ditt företag kan behöva flera domännamn för olika ändamål. Du kanske till exempel vill lägga till en annan stavning av ditt företagsnamn eftersom kunderna redan använder det och deras meddelanden inte har nå dig.

## <a name="try-it"></a>Prova!

1. I administrationscentret för Microsoft 365 väljer du **Konfigurera**.
1. Under **Konfigurera din egen domän väljer** du **Visa**.
1. Välj **Manage** och sedan **Add domain**.
1. Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa**.
1. Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**
1. Logga in på din registrator om du uppmanas till det och välj sedan **Godkänn**.
1. Välj **Add the DNS records for me** och sedan **Next**.
1. Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som ska hanteras av en annan domän. Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna **för Skype** för företag och Hantering av mobila enheter för **Office 365.**
1. Välj **Nästa,** **Godkänn** **, Nästa** och sedan **Slutför.** Din nya domän har lagts till.

Om du vill ta emot e-post på din nya domän måste du lägga till ett nytt e-postalias för varje användare:

1. Välj **Användare**, **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.
1. Välj **Hantera e-postalias** och sedan Lägg **till ett alias**.
1. Ange användarnamnet och välj sedan den nya domänen i listrutan.
1. Välj **Spara** ändringar och stäng sedan fönstret.
1. Upprepa de här stegen för alla användare som ska få e-post på den nya domänen.

## <a name="related-content"></a>Relaterat innehåll

Lägga till en domän i [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (artikel) Lägga till [DNS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för att ansluta din domän (artikel) Ändra namnservrar för att konfigurera [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) med valfri domänregistrator (artikel) [Vanliga](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) frågor och svar om domäner (artikel)