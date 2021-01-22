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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du hanterar konfigurera principer för skydd mot dataförlust.
ms.openlocfilehash: e963cf85fee887b6e91c6e54b00aaa9e5174e3b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927964"
---
# <a name="prevent-data-loss-with-dlp"></a>Förhindra dataförlust med DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Principer för dataförlustskydd hjälper till att identifiera och skydda känslig information inom företaget, t.ex. personnummer eller journaler. 

## <a name="try-it"></a>Prova!

1. Kom igång genom att gå till [administrationscentret](https://admin.microsoft.com)och välja **Installation.**
1. Rulla ned till **Konfigurera skydd mot dataförlust** och välj sedan **Visa** och sedan **Hantera.**
1. Om du vill redigera en princip markerar du den, **väljer Redigera princip** och sedan vad du vill ändra. Välj till exempel Platser **om du vill** ändra det som genomsöks.
1. Om du vill aktivera genomsökning av innehåll i Microsoft Teams ändrar du växlingsknappen till **läget** På och väljer sedan **Spara.**
1. Om du vill redigera principinställningarna väljer du **Redigera.**
1. Du måste ange separata regler som gäller för små och stora mängder känsligt innehåll som upptäckts. Utöka regeln för låg volym. Välj **Redigera regel.**
1. Granska inställningarna och justera dem efter behov. Du kan till exempel välja att anpassa **texten i e-postmeddelandet** **och anpassa texten i principtipset.** Välj **Spara**.
1. Upprepa för regeln med hög volym. Välj **Spara** och sedan **Stäng.**
1. Om du vill skapa en ny princip väljer **du Skapa en princip.**
1. Du kan skapa en anpassad princip eller utgå från en mall. Om du till exempel vill skapa en  HIPAA-policy väljer du mallen Medicinskt och hälsa och sedan **U.S. Health Insurance Act (HIPAA).** Välj **Nästa**.
1. Ange ett namn och en beskrivning för principen. Välj **Nästa**.
1. Välj platser att söka igenom. Välj **Nästa**.
1. Välj den typ av innehåll som du vill skydda. Välj **Nästa**.
1. Välj vad du vill ska hända om känslig information identifieras. Välj **Nästa**.
1. Anpassa åtkomst och åsidosätta behörigheter. Välj **Nästa**.
1. Välj när principen ska gälla. Välj **Nästa**.
1. Granska inställningarna och välj **Skapa.** När principen börjar gälla blockeras e-postmeddelanden som innehåller den beskrivande känsliga informationen och avsändaren som försökte skicka informationen visas ett varningsmeddelande.