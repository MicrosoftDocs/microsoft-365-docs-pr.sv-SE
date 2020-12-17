---
title: Förhindra dataförlust
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
description: Lär dig hur du hanterar inställningar för att förhindra data förlust.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702908"
---
# <a name="prevent-data-loss-with-dlp"></a>Förhindra data förlust med DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Principer för skydd mot data förlust hjälper dig att identifiera och skydda företagets känslig information, till exempel sociala säkerhets nummer eller medicinska uppgifter. 

## <a name="try-it"></a>Prova!

1. För att komma igång går du till [administrations centret](https://admin.microsoft.com)och väljer **Installera**.
1. Rulla ned för att **Konfigurera data förlust skydd** och välj sedan **Visa** och sedan **Hantera**.
1. Om du vill redigera en princip markerar du den, väljer **Redigera princip** och väljer sedan vad du vill ändra. Välj till exempel **platser** för att ändra vad som ska skannas.
1. Om du vill aktivera genomsökning av innehåll i Microsoft Teams aktiverar du växlings knappen **till position och** väljer sedan **Spara**.
1. Om du vill redigera princip inställningar väljer du **Redigera**.
1. Du måste ange separata regler som gäller för små och stora mängder av känsligt innehåll. Utöka din regel för dålig volym. Välj **Edit Rule**.
1. Granska inställningarna och justera dem efter behov. Du kan till exempel välja att **Anpassa e-** postmeddelandet och **Anpassa princip Tips texten**. Välj **Spara**.
1. Upprepa för den högsta volym regeln. Välj **Spara** och sedan **Stäng**.
1. Om du vill skapa en ny princip väljer du **skapa en princip**.
1. Du kan skapa en anpassad princip eller börja med en mall. Om du till exempel vill skapa en HIPAA policy väljer du hälso mal len **medicin och hälsa** och väljer sedan **amerikansk sjukförsäkring Act (HIPAA)**. Välj **Nästa**.
1. Ange ett namn och en beskrivning för policyn. Välj **Nästa**.
1. Välj var du vill skanna. Välj **Nästa**.
1. Välj den typ av innehåll som du vill skydda. Välj **Nästa**.
1. Välj vad du vill ska hända om känslig information upptäcks. Välj **Nästa**.
1. Anpassa dina åtkomst-och behörighets behörigheter. Välj **Nästa**.
1. Välj när du vill att principen ska börja gälla. Välj **Nästa**.
1. Granska inställningarna och välj **skapa**. När din policy har verkställts blockeras e-post som innehåller den beskrivna känslig informationen och avsändaren som försökte skicka den informationen får ett varnings meddelande.