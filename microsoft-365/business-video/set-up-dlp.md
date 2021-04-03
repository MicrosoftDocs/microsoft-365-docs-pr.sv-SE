---
title: Förhindra dataförlust
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
description: Lär dig hur du hanterar principer för skydd mot dataförlust.
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580444"
---
# <a name="prevent-data-loss-with-dlp"></a>Förhindra dataförlust med DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Principer för dataförlustskydd hjälper till att identifiera och skydda känslig information inom företaget, t.ex. personnummer eller journaler. 

## <a name="try-it"></a>Prova!

1. Kom igång genom att gå till [administrationscentret](https://admin.microsoft.com)och välja **Inställningar.**
1. Rulla ned till **Konfigurera skydd mot dataförlust** och välj sedan **Visa** och **hantera**.
1. Om du vill redigera en princip markerar du den, **väljer Redigera princip** och väljer sedan vad du vill ändra. Välj till exempel **Platser om du vill** ändra vad som genomsöks.
1. Om du vill aktivera genomsökning av innehåll i Microsoft Teams ändrar du växlingsknappen **till** läget På och väljer sedan **Spara**.
1. Om du vill redigera principinställningarna väljer du **Redigera**.
1. Du måste ange separata regler som gäller för små och stora mängder känsligt innehåll som upptäckts. Utöka regeln för låg volym. Välj **Redigera regel.**
1. Granska inställningarna och justera dem efter behov. Du kan till exempel välja att Anpassa **e-posttexten** **och Anpassa texten med principtips.** Välj **Spara**.
1. Upprepa för regeln om hög volym. Välj **Spara** och sedan **Stäng.**
1. Om du vill skapa en ny princip väljer **du Skapa en princip**.
1. Du kan skapa en anpassad princip eller utgå från en mall. Om du till exempel vill skapa en HIPAA-policy väljer du mallen Medical **and health** och sedan **U.S. Health Insurance Act (HIPAA).** Välj **Nästa**.
1. Ange ett namn och en beskrivning för principen. Välj **Nästa**.
1. Välj platser att söka igenom. Välj **Nästa**.
1. Välj den typ av innehåll som du vill skydda. Välj **Nästa**.
1. Välj vad du vill ska hända om känslig information identifieras. Välj **Nästa**.
1. Anpassa åtkomst och åsidosätta behörigheter. Välj **Nästa**.
1. Välj när du vill att principen ska gälla. Välj **Nästa**.
1. Granska inställningarna och välj **Skapa**. När principen börjar gälla kommer e-post som innehåller den beskrivna känsliga informationen att blockeras och avsändaren som försökte skicka informationen ser ett varningsmeddelande.