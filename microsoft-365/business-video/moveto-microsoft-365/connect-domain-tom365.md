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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ansluter din domän till Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925116"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Anslut domän till Microsoft 365 för företag

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

När du har ställt Microsoft 365 och flyttat dina e-postdata från Google Workspace kan du ansluta din domän till Microsoft 365. 

Först måste du ta bort befintliga DNS-poster från Google och sedan kan vi lägga till nya DNS-poster från Microsoft 365.

## <a name="try-it"></a>Prova själv!

1. Logga in på administratörskonsolen för Google Workspace [admin.google.com](https://admin.google.com).
1. Välj **Domäner**, **Hantera domäner**, Visa **information**, Hantera **domän** och sedan **DNS i** det vänstra navigeringsfältet.
1. Rulla ned till **Förendringsposter**, **öppna Google Workspace**, välj **Ta** bort och sedan **Ta bort** igen.
1. Bläddra ned till **Anpassade resursposter och** ta bort alla befintliga DNS-poster som visas, inklusive de som du har skapat tidigare för Microsoft 365.
1. Gå till [Microsoft 365 administrationscentret.](https://admin.microsoft.com)
1. I det vänstra navigeringsfältet väljer **du Visa alla**, **Inställningar**, **Domäner**.
1. Välj sedan standarddomän.
1. Välj **Fortsätt installationen** och anslut sedan din domän genom att välja **Fortsätt.**
1. Rulla nedåt för att visa de DNS-poster som måste kopieras till Google.
1. Öppna **MX Records** och kopiera posten under **Pekar** på adress eller värde.
1. Gå tillbaka till Google. I **avsnittet Custom resource records öppnar** du listrutan posttyp och väljer **MX.**
1. Klistra in posten du kopierade i fältet **Data.**
1. Välj sedan **Lägg till**.
1. Upprepa processen för CNAME- och TXT-poster och lägg till värdena på sidan för Google DNS-hantering.
1. Gå tillbaka till Microsoft 365 och välj **Fortsätt.**

    Domänkonfigurationen är klar.