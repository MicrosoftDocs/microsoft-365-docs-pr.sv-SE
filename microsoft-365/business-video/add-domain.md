---
title: Lägga till en domän
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du lägger till en annan domän i din prenumeration.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927616"
---
# <a name="add-another-domain"></a>Lägga till en annan domän

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ditt företag kan behöva flera domännamn för olika ändamål. Du kanske till exempel vill lägga till en annan stavning av företagsnamnet eftersom kunderna redan använder det och deras meddelanden inte har nå dig.

## <a name="try-it"></a>Prova!

1. Välj Installation i administrationscentret för Microsoft 365.
1. Välj Visa **under Konfigurera din** egen **domän.**
1. Välj **Hantera** och sedan **Lägg till domän.**
1. Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa.**
1. Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**
1. Logga in på registratorn om du uppmanas till det och välj **sedan Godkänn.**
1. Välj **Lägg till DNS-posterna åt** mig och välj sedan **Nästa.**
1. Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som kommer att hanteras av en annan domän. Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna för **Skype** för företag och Hantering av mobila enheter för **Office 365.**
1. Välj **Nästa,** **Godkänn,** Nästa och sedan **Slutför.**  Din nya domän har lagts till.

Om du vill ta emot e-post på den nya domänen måste du lägga till ett nytt e-postalias för varje användare:

1. Välj **Användare,** **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.
1. Välj **Hantera e-postalias** och sedan **Lägg till ett alias.**
1. Ange användarnamnet och välj sedan den nya domänen i listrutan.
1. Välj **Spara ändringar** och stäng sedan fönstret.
1. Upprepa dessa steg för alla användare som ska få e-post på den nya domänen.