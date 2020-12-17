---
title: Konfigurera skydd mot nätfiske
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
description: Lär dig hur du konfigurerar skydd mot nätfiske.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702893"
---
# <a name="set-up-anti-phishing"></a>Konfigurera anti-nätfiske

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

Nätfiske är en skadlig attack där en e-postadress ser ut som om den skickades från en bekant källa, men försöker samla in personlig information. Som standard inkluderar Microsoft 365 ett visst skydd mot nätfiske, men du kan öka detta skydd genom att förfina inställningarna. Låt oss ta en titt.

## <a name="try-it"></a>Prova!

1. I Admin Center på [https://admin.microsoft.com](https://admin.microsoft.com) väljer du **säkerhet**, **Threat Management**, **policy** och sedan **ATP-nätfiske**.
1. Välj **standard princip** för att förfina den.
1. I avsnittet **personifiering** väljer du **Redigera**.
1. Gå till **Lägg till domäner för att skydda** och välj växlings knappen för att automatiskt inkludera de domäner du äger.
1. Gå till **åtgärder**, öppna List rutan **om e-post skickas av en personifierad användare** och välj den åtgärd du vill använda.

    Öppna List rutan **om e-post skickas av en domänkontrollant** och välj den åtgärd du vill använda.
1. Välj **Aktivera säkerhets tips**. Välj om du vill få tips för användarna när systemet identifierar personifierade användare, domäner eller ovanliga tecken. Välj **Spara**.
1. Välj **post lådans intelligens** och kontrol lera att den är aktive rad. Detta gör att din e-post blir mer effektiv genom användnings mönster.
1. Välj **Lägg till betrodda avsändare och domäner**. Här kan du lägga till e-postadresser eller domäner som inte ska klassificeras som en personifiering.
1. Välj **Granska dina inställningar**, kontrol lera att alla stämmer, Välj **Spara** och sedan **Stäng**.

    Nu har din organisation bättre skydd mot nätfiske-hot.