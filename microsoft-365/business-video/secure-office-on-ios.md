---
title: Säkra Office-appar på iOS
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
description: Lär dig hur du skyddar Office-appar på iOS med Microsoft 365 Business Premium.
ms.openlocfilehash: fd7fdd32500f9a2362ac29059abe9424d045c206
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928036"
---
# <a name="secure-office-apps-on-ios"></a>Säkra Office-appar på iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Du kan konfigurera en princip för användaråtkomst som kräver att mobila användare anger en PIN-kod eller ett fingeravtryck när de loggar in, och krypterar även arbetsfiler som lagras på deras enheter.

## <a name="try-it"></a>Prova!

1. Logga in på administrationscentret för Microsoft 365.
1. Välj **Lägg till** princip under **Principer.**
1. I fönstret **Lägg till** princip anger du ett namn under **Principnamn** och väljer den principtyp som du vill använda under **Principtyp.**
1. Aktivera Hantera **hur användare kommer åt Office-filer på mobila** enheter och kontrollera att följande tre inställningar är aktiverat:
    - **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program**
    - **Skydda arbetsfiler om enheter försvinner eller blir stulna**
    - **Kryptera arbetsfiler**

1. Under **Filer i de här apparna skyddas** markerar du de Office-program som du vill skydda på mobila enheter.
1. Under **Vem får de här inställningarna?** är alla användare  valda som standard, men du kan välja Ändra för att välja de säkerhetsgrupper som du har skapat.
1. Välj Lägg till för att slutföra **principen.**
1. Välj Stäng **på sidan** Lägg till **princip.**
1. På startsidan för administrationscentret bekräftar du att den nya principen har lagts till genom att välja **Principer** och granska principen på **sidan** Principer.