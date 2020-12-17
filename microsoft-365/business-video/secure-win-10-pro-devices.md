---
title: Hantera principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium
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
description: Lär dig att hantera principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703193"
---
# <a name="manage-windows-10-pro-device-policies"></a>Hantera principer för Windows 10 Pro-enheter

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

Du kan använda Microsoft 365 Business för att kontrol lera att Windows Defender Antivirus är aktiverat på Windows 10-enheter och att Microsoft Updates laddas ned automatiskt till användarnas enheter.

## <a name="try-it"></a>Prova!

1. Logga in på administrationscentret för Microsoft 365.
1. Under **principer** väljer du Lägg till princip.
1. Ange ett namn under **princip namn** i fönstret **Lägg till policy** och välj sedan **Windows 10-enhets konfiguration** under **princip typ**.
1. Välj **säkra Windows 10-enheter** för att se under Inställningar.
1. Se till att **skydda datorer mot virus och andra hot med Windows Defender Antivirus** och **hålla Windows 10-enheter uppdaterade automatiskt** .
1. Under **vem får de här inställningarna?** är alla användare **markerade som standard** , men du kan välja att välja vilka säkerhets grupper du har skapat.
1. Klicka på **Lägg till** för att slutföra skapandet av principen.
1. På sidan **Lägg till princip** väljer du **Stäng**.
1. På Start sidan för administrations centret kontrollerar du att den nya principen har lagts till genom att välja **principer** och granska din policy på sidan **policys** .
1. Verifiera att principen har verkställts genom att gå till Windows Update på en användares Windows 10-enhet, välja **Avancerade alternativ** och bekräfta att inställningarna är nedtonade.

    Klicka sedan på **Välj hur uppdateringar levereras** och kontrol lera att inställningarna är nedtonade och att följande meddelande visas: **vissa inställningar är dolda eller hanteras av din organisation**.

