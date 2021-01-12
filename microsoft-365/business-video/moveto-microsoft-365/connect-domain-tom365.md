---
title: Anslut din domän till Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Lär dig hur du ansluter din domän till Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794708"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Ansluta din domän till Microsoft 365 för företag

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

När du har konfigurerat Microsoft 365 och flyttat dina e-postdata från Google Workspace kan du ansluta domänen till Microsoft 365. 

Först måste du ta bort befintliga DNS-poster från Google och sedan kan vi lägga till nya DNS-poster från Microsoft 365.

## <a name="try-it"></a>Prova!

1. Logga in på din Google Workspace-administratörskonsolen på [admin.Google.com](https://admin.google.com).
1. Välj **domäner**, **hantera domäner**, **Visa information**, **Hantera domän** och sedan **DNS** i det vänstra navigerings fältet.
1. Bläddra ned till **syntetiska poster**, öppna **Google Workspace**, Välj **ta bort** och sedan **ta bort** igen.
1. Bläddra ned till **anpassade resurs poster** och ta bort alla befintliga DNS-poster som visas, inklusive de som du tidigare har skapat för Microsoft 365.
1. Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).
1. I det vänstra navigerings fältet väljer du, **Visa alla**, **Inställningar**, **domäner**.
1. Välj sedan standard domänen.
1. Välj **Fortsätt installationen** och välj sedan  **Fortsätt** för att ansluta domänen.
1. Bläddra nedåt för att visa de DNS-poster som måste kopieras till Google.
1. Öppna **MX-poster** och kopiera posten under **pekar på adress eller värde**.
1. Gå tillbaka till Google och öppna avsnittet **anpassade resurs poster** och välj **MX**.
1. Klistra in den post du kopierade i fältet **data** .
1. Välj sedan **Lägg till**.
1. Upprepa processen för CNAME-och TXT-poster och Lägg till värdena på sidan Google DNS Management.
1. Gå tillbaka till administrations centret för Microsoft 365 och välj **Fortsätt**.

    Domän konfigurationen är klar.