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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skyddar Office-appar på iOS med Microsoft 365 Business Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702655"
---
# <a name="secure-office-apps-on-ios"></a>Säkra Office-appar på iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Du kan konfigurera en användar åtkomst princip som kräver att mobila användare anger en PIN-kod eller ett finger avtryck för att logga in och dessutom krypterar filer som lagras på deras enheter.

## <a name="try-it"></a>Prova!

1. Logga in på administrationscentret för Microsoft 365.
1. Under **principer** väljer du **Lägg till princip**.
1. Ange ett namn under **princip namn** i fönstret **Lägg till princip** och välj den princip typ som du vill använda under **princip typ**.
1. Aktivera **hantera hur användare kommer åt Office-filer på mobila enheter** och kontrol lera att följande tre inställningar är aktiverade:
    - **Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program**
    - **Skydda arbetsfiler när enheter försvinner eller blir stulna**
    - **Kryptera arbetsfiler**

1. Under **filer i de här apparna skyddas** väljer du de Office-program som du vill skydda på mobila enheter.
1. Under **vem får de här inställningarna?** är alla användare **markerade som standard** , men du kan välja att välja vilka säkerhets grupper du har skapat.
1. Klicka på **Lägg till** för att slutföra skapandet av principen.
1. På sidan **Lägg till princip** väljer du **Stäng**.
1. På Start sidan för administrations centret kontrollerar du att den nya principen har lagts till genom att välja **principer** och granska din policy på sidan **policys** .