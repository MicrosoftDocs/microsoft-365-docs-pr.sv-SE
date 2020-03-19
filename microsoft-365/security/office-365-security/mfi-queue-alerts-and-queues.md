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
description: Administratörer kan lära sig mer om köaviseringar och köer i instrumentpanelen för e-postflöde i Säkerhets- & Compliance Center.
ms.openlocfilehash: bc777e3c9764987dc72aa0407f19618bc26f7528
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812962"
---
# <a name="queue-alerts-and-queues"></a>Köaviseringar och köer

## <a name="queue-alerts"></a>Köaviseringar

När meddelanden inte kan skickas från din Office 365-organisation till lokala e-postservrar eller partnerservrar med hjälp av kopplingar köas meddelandena i Office 365. Vanliga exempel som orsakar detta villkor är:

- Anslutningen är felaktigt konfigurerad.

- Det har skett nätverks- eller brandväggsändringar i den lokala miljön.

Office 365 fortsätter att försöka leverera igen i 24 timmar. Efter 24 timmar upphör meddelandena att gälla och returneras till avsändarna i rapporter som inte levereras (kallas även en NDRs eller avvisningsmeddelanden).

Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 2000-meddelanden) kommer aviseringarna att vara tillgängliga i instrumentpanelen för e-postflödet vid **senaste aviseringar**och administratörer får ett e-postmeddelande (till deras alternativa e-postadress). Information om hur du konfigurerar tröskelvärdet för aviseringar, daglig meddelandegräns och/eller mottagare av aviseringen finns i avsnittet **Anpassa köaviseringar** nedan.

![Köaviseringar i det senaste varningsområdet för instrumentpanelen för e-postflöde i Säkerhets-& Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Anpassa köaviseringar

E-postflödesinsikter skapar en varningsprincip med namnet **Meddelanden har försenats** (kryssrutan **Skicka e-postmeddelanden** i exempelskärmbilden nedan) som finns i **varningsprinciper**för **aviseringar** \> . Du kan ändra tröskelvärdet och varningsmottagarna genom att klicka på principen.

![Varningar Navigering](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Du ser ett nytt principinformationsblad, du kan nu klicka på **Redigera princip**.

![Redigera princip](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

Informationsbladet ändras till **redigeraprincipen**. Du kan nu ändra mottagarna för e-postmeddelandet för aviseringar, gränsen för antalet meddelanden som skickas per dag och minimitröskeln för att utlösa aviseringen (200 eller fler).

![Redigera principblad](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Information om köavisering

När du klickar på aviseringen visas varningsinformationen i ett utfällbart fönster.

![Välj en köavisering i området Senaste aviseringar i instrumentpanelen för e-postflöde i Säkerhets- & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Utfällbara köaviseringsinformation i säkerhets& Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

Du kan klicka på **Visa kö** i varningsinformationen om du vill visa köinformation, problem och länkar till tillgängliga korrigeringar i ett nytt utfällbart fönster.

![Utfällbara köaviseringsinformation i säkerhets& Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visa kö i varningsinformationen](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Köer

Även om den köade meddelandevolymen inte har överskridit tröskelvärdet kan du fortfarande använda området **Köer** på instrumentpanelen för e-postflöde för att se meddelanden som har köati i mer än en timme. Du kan använda området **Köer** för att övervaka antalet köade meddelanden (värdet 0 anger att e-postflödet är OK) och vidta åtgärder innan antalet köade meddelanden blir för stort.

![Köer i instrumentpanelen för e-postflöde i Säkerhets-& Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

När du klickar på antalet köade meddelanden i **köer**visas köinformationen och vägledningen för hur problemet ska åtgärdas i ett utfällbart fönster (samma utfällbara fönster som visas när du har klickat på **Visa kö** i informationen om en köavisering).

![Köinformation](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter om e-postflöde på instrumentpanelen för e-postflöde finns [i E-postflödesinsikter i Security & Compliance Center](mail-flow-insights-v2.md).
