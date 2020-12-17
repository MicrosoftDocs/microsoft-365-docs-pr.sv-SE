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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du lägger till en annan domän i prenumerationen.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702786"
---
# <a name="add-another-domain"></a>Lägga till en annan domän

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ditt företag kan behöva flera domän namn för olika ändamål. Du kanske till exempel vill lägga till en annan stavning i ditt företags namn eftersom kunderna redan använder det och att kommunikationen mellan dem är misslyckad.

## <a name="try-it"></a>Prova!

1. Välj **installation** i administrations centret för Microsoft 365.
1. Välj **Visa** under **Konfigurera din anpassade domän**.
1. Välj **Hantera** och sedan **Lägg till domän**.
1. Ange det nya domän namnet som du vill lägga till och välj sedan **Nästa**.
1. Logga in på din domän registrator i det här fallet GoDaddy och välj sedan **Nästa**.
1. Om du uppmanas att göra det loggar du in på din registrator och väljer sedan **auktorisera**.
1. Välj **Lägg till DNS-posterna åt mig** och välj sedan **Nästa**.
1. Välj tjänster för den nya domänen och avmarkera kryss rutorna för de tjänster som ska hanteras av en annan domän. Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryss rutorna för hantering av **Skype för företag** och **mobila enheter för Office 365**.
1. Välj **Nästa**, **auktorisera**, **Nästa** och sedan **Slutför**. Den nya domänen har lagts till.

Om du vill ta emot e-post från din nya domän måste du lägga till ett nytt e-postalias för varje användare:

1. Välj **användare**, **aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.
1. Välj **Hantera e-postalias** och **Lägg sedan till ett alias**.
1. Ange användar namnet och välj sedan den nya domänen i list rutan.
1. Välj **Spara ändringar** och stäng sedan fönstret.
1. Upprepa de här stegen för varje användare som ska ta emot e-post på den nya domänen.