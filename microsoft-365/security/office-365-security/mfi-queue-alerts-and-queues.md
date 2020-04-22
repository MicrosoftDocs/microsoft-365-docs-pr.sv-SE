---
title: Köaviseringar och köer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära sig mer om köaviseringar och köer i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 7bb103bad89ee39991a5c16d7101ab4658842479
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635190"
---
# <a name="queue-alerts-and-queues"></a>Köaviseringar och köer

## <a name="queue-alerts"></a>Köaviseringar

När meddelanden inte kan skickas från din organisation till dina lokala eller partner-e-postservrar med hjälp av anslutningsappar, står meddelandena i kö i Office 365. Vanliga exempel som orsakar detta tillstånd är:

- Anslutningen är felaktigt konfigurerad.

- Det har skett nätverks- eller brandväggsändringar i din lokala miljö.

Microsoft 365 fortsätter att försöka levereras igen i 24 timmar. Efter 24 timmar upphör meddelandena att gälla och returneras till avsändarna i rapporter som inte levereras (kallas även ndr-meddelanden eller avstudsar).

Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 2000-meddelanden) är aviseringarna tillgängliga i instrumentpanelen för e-postflödet vid **de senaste aviseringarna**och administratörer får ett e-postmeddelande (till deras alternativa e-postadress). Information om hur du konfigurerar varningströskeln, den dagliga meddelandegränsen och/eller mottagarna av aviseringen finns i avsnittet **Anpassa köaviseringar** nedan.

![Kövarningar i området Senaste aviseringar i instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Anpassa köaviseringar

Statistik för e-postflöde skapar en aviseringsprincip med namnet **Meddelanden har försenats** (kryssrutan **Skicka e-postmeddelanden** i exempelskärmen nedan) som finns i **varningsprinciper** \> **Alert Policies**för aviseringar . Du kan ändra tröskelvärdet och varna mottagarna genom att klicka på principen.

![Navigering i varningar](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Du ser ett nytt policyinformationsblad, du kan nu klicka på **Redigera princip**.

![Redigera princip](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

Informationsbladet ändras till **redigeringsprincipen**. Du kan nu ändra mottagarna för aviseringsmeddelandet, gränsen för antalet meddelanden som skickas per dag och minimitröskeln för att utlösa aviseringen (200 eller fler).

![Redigera principblad](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Information om köavisering

När du klickar på aviseringen visas varningsinformationen i ett utfällbart fönster.

![Välj en köavisering i området Senaste aviseringar på instrumentpanelen för e-postflödet i Säkerhets- & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Köaviseringsinformationen Utfällbara information i Security & Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

Du kan klicka på **Visa kö** i aviseringsinformationen om du vill se köinformation, problem och länkar till tillgängliga korrigeringar i ett nytt utfällbart fönster.

![Köaviseringsinformationen Utfällbara information i Security & Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visa kö i varningsinformationen](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Köer

Även om den köade meddelandevolymen inte har överskridit tröskelvärdet kan du fortfarande använda området **Köer** på instrumentpanelen för e-postflödet för att se meddelanden som har köats i mer än en timme. Du kan använda **området Köer** för att övervaka antalet meddelanden i kö (värdet 0 anger att e-postflödet är OK) och vidta åtgärder innan antalet köade meddelanden blir för stort.

![Köer i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

När du klickar på antalet meddelanden i kö **i Köer**visas köinformation och vägledning för hur du åtgärdar problemet i ett utfällbart fönster (samma utfällbara objekt som visas när du klickar på **Visa kö** i information om en köavisering).

![Köinformation](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Snabbreferens

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
