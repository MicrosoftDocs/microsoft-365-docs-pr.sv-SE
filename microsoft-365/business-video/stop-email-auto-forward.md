---
title: Stoppa e-postvidarebefordrade meddelanden automatiskt
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
description: Lär dig hur du stoppar automatisk vidarebefordran av e-post.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702595"
---
# <a name="stop-email-auto-forward"></a>Stoppa automatisk vidarebefordran av e-post

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Om en hackare får åtkomst till en användares post låda kan de automatiskt vidarebefordra användarens e-post till en extern adress och stjäla ägande information. Du kan stoppa det genom att skapa en regel för e-postflöde.

## <a name="try-it"></a>Prova!

1. I Microsoft 365 Admin Center väljer du **Exchange**, **mail flöde** och på fliken **regler** väljer du plus tecknet och väljer **skapa en ny regel**.
1. Välj **fler alternativ**. Namnge den nya regeln.
1. Öppna sedan den nedrullningsbara List rutan för **Använd den här regeln om**, Välj **avsändaren** och sedan **är extern intern**.
1. Välj **inuti organisationen** och sedan **OK**.
1. Välj **Lägg till villkor**, öppna List rutan, Välj **meddelande egenskaperna** och ange sedan **meddelande typen**.
1. Öppna List rutan **Välj meddelande typ** , Välj **Auto-Forward** och sedan **OK**.
1. Öppna den nedrullningsbara List rutan **gör följande** , Välj **blockera meddelandet** **och ignorera sedan meddelandet och ta med en förklaring**.
1. Ange meddelande texten för din förklaring och välj sedan **OK**.
1. Bläddra längst ned och välj **Spara**.

    Din regel har skapats och hackare kommer inte längre att kunna Vidarekoppla meddelanden automatiskt.