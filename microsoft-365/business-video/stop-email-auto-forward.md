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
description: Lär dig hur du stoppar automatisk vidarebefordran av e-postmeddelanden genom att skapa en e-postflödesregel för att undvika stöld av upphovsrättsskyddad information.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706480"
---
# <a name="stop-email-auto-forward"></a>Stoppa vidarebefordran av e-post automatiskt

## <a name="watch-stop-auto-forwarding-emails"></a>Titta på: Stoppa e-postmeddelanden om automatisk vidarebefordran

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Om en hackare får åtkomst till en användares postlåda kan de automatiskt vidarebefordra användarens e-post till en adress utanför företaget och stjäla egen information. Du kan stoppa detta genom att skapa en e-postflödesregel.

## <a name="try-it"></a>Prova själv!

1. I Microsoft 365 väljer du **Exchange**, e-postflöde och på  fliken Regler väljer du plustecknet och **väljer skapa en ny regel.** 
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

[Lägga till ytterligare ett e-postalias för en användare](../admin/email/add-another-email-alias-for-a-user.md) (artikel)\
[Konfigurera vidarebefordran av e-post i Microsoft 365](../admin/email/configure-email-forwarding.md) (artikel)\
[Hitta och korrigera problem med e-postleverans som Office 365 för företag-administratör](/exchange/troubleshoot/email-delivery/email-delivery-issues) (artikel)