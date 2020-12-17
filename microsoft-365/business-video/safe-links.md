---
title: Hantera säkra länkar
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
description: Lär dig hur du hanterar säkra Länkar för att skydda ditt företag från skadliga webbplatser.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702665"
---
# <a name="manage-safe-links"></a>Hantera säkra länkar

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender för Office 365, kallades tidigare Microsoft 365 ATP eller Avancerat skydd, hjälper till att skydda ditt företag mot skadliga webbplatser när personer klickar på länkar i Office-program.

## <a name="try-it"></a>Prova!

1. Gå till [administrations centret](https://admin.microsoft.com)och välj **Installera**.
1. Rulla nedåt för att **öka skyddet mot avancerade hot**. Välj **Visa**, **Hantera** och sedan **ATP-säkra länkar**.
1. Under **principer som gäller för hela organisationen** väljer du **standard** principen och sedan **redigerings** ikonen.
1. Ange en URL som du vill blockera.
1. Välj **Använd säkra länkar i Office-program, Office för iOS och Android**. Välj **Spåra inte när användare klickar på säkra länkar**; och välj **Tillåt inte att användare klickar via säkra länkar till original-URL: en**. Dessa kanske redan är markerade om du har ställt in standard policyn. Välj **Spara**.
1. Välj **regel för rekommenderade säkra länkar** under **principer som gäller för specifika mottagare** och välj sedan **redigerings** ikonen.
1. Välj **Inställningar**, Bläddra ned, ange den URL som du inte vill ska markeras och välj sedan ikonen **Lägg till** .
1. Välj **tillämpas på** och välj sedan ditt domän namn. Markera de ytterligare domäner som du vill tillämpa regeln på. Välj **Lägg till**, **OK** och sedan **Spara**.

Nu har du konfigurerat ATP-länkar. Tillåt upp till 30 minuter innan ändringarna börjar gälla.

När en användare får ett e-postmeddelande med länkar genomsöks länkarna. Om länkarna betraktas som säkra kan de vara Klicka bara på dem. Om länken finns i blockeringslistan visas ett meddelande om att det har blockerats.