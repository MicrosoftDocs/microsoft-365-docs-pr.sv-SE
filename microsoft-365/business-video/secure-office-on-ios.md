---
title: Säkra Office-appar på iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Lär dig hur du skyddar Office-appar på iOS med Microsoft 365 Business Premium.
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580468"
---
# <a name="secure-office-apps-on-ios"></a>Säkra Office-appar på iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Du kan konfigurera en princip för användaråtkomst som kräver att mobila användare anger en PIN-kod eller ett fingeravtryck när de loggar in. Dessutom krypteras arbetsfiler som lagras på deras enheter.

## <a name="try-it"></a>Prova själv!

1. Logga in på administrationscentret för Microsoft 365.
1. Välj **Lägg** till princip **under Principer.**
1. I fönstret **Lägg till** princip anger du ett namn under **Principnamn** och väljer den principtyp du vill använda under **Principtyp.**
1. Aktivera Hantera **hur användare kommer Office filer på mobila** enheter och kontrollera sedan att följande tre inställningar är aktiverat:
    - **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program**
    - **Skydda filer om enheter försvinner eller blir stulna**
    - **Kryptera arbetsfiler**

1. Under **Filer i de här apparna skyddas** väljer du det Office ska skydda på mobila enheter.
1. Under **Vem de här inställningarna?** är alla användare markerade som  standard, men du kan välja Ändra och välja de säkerhetsgrupper som du har skapat.
1. Välj Lägg till för att slutföra **principen.**
1. På sidan **Lägg till princip** väljer du **Stäng.**
1. På startsidan för administrationscentret bekräftar du att den nya principen har lagts till genom att välja **Principer** och granska principen på **sidan** Principer.