---
title: Stoppa e-post med automatisk vidarebefordring
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Lär dig hur du stoppar automatisk vidarebefordran av e-postmeddelanden.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903688"
---
# <a name="stop-email-auto-forward"></a>Stoppa vidarebefordran av e-post automatiskt

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information. Du kan stoppa detta genom att skapa en e-postflödesregel.

## <a name="try-it"></a>Prova!

1. I administrationscentret för Microsoft 365 väljer du **Exchange** **,** e-postflöde och på fliken Regler väljer du plustecknet och **sedan Skapa en ny regel.** 
1. Välj **Fler alternativ.** Ge den nya regeln ett namn.
1. Öppna sedan listrutan för att **tillämpa regeln om**, välj avsändaren **och** sedan är **extern intern**.
1. Välj **Inom organisationen** och sedan **OK.**
1. Välj **Lägg till** villkor , öppna listrutan, välj Egenskaper för **meddelande** och inkludera **sedan meddelandetypen**.
1. Öppna **listrutan välj** meddelandetyp, välj **Vidarebefordra automatiskt** och sedan **OK.**
1. Öppna **listrutan Gör följande,** välj **Blockera meddelandet och avvisa** sedan meddelandet och ge en **förklaring**.
1. Ange meddelandetexten för din förklaring och välj **sedan OK.**
1. Rulla längst ned och välj **Spara**.

    Din regel har skapats och hackare kommer inte längre att kunna vidarebefordra meddelanden automatiskt.

## <a name="related-content"></a>Relaterat innehåll

Lägga till ytterligare [ett e-postalias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) för en användare (artikel) Konfigurera vidarebefordran av e-post i [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (artikel) Hitta och korrigera problem med e-postleverans som administratör för [Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) för företag (artikel)