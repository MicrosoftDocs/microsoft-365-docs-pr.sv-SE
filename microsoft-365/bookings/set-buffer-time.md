---
title: Ange buffertstorlek i Microsoft-bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Ange buffertstorlek före eller efter en avtalad tid i Microsoft-bokningar för att möjliggöra tid för rensning eller återställning av utrustning.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962353"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Ange buffertstorlek i Microsoft-bokningar

Vissa av dina avtalade tider kanske kräver tid innan eller efter det att du har träffat med din kund för att konfigurera, rensa eller återställa rummet och utrustningen. Om du befinner dig på resan mellan avtalade tider med kunder kan du behöva tid för att se till att du och ditt team kan resa mellan avtalade tider utan att behöva vänta på att kunden väntar.

Du kan ange buffertstorlek innan avtalade tider börjar efter att avtalade tider slutar eller båda för att ge personalen den tid de behöver för att förbereda nästa avtalade tid.

## <a name="set-buffer-time-defaults"></a>Ange tids inställningar för buffert

Tids inställningar för buffert är inställda på sidan **tjänst information** i bokningar. Precis som alla tjänst standarder är inställda på den här sidan kan dessa standardvärden redige ras av dig för en viss bokning för att uppfylla specifika kund behov.

Inställningen för buffertlängd visas precis under **Standard längden** på sidan med **service information** . Innan den kan anges för en viss tjänst måste du aktivera inställningen för buffertstorlek genom att välja växlings knappen för bufferten. Detta gör att List rutorna **före** och **efter** visas, vilka används för att välja den standard tid som ska behållas före och efter varje bokning, som du ser här:

   ![Bild av bokningar med buffertstorlek aktiverat](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tids inställning för buffert och avtalad tid

För att slippa förvirring när kunderna förväntar sig att mötas kan du Visa tidsenheter och faktisk avtalad tid (den tid kunderna förväntar sig att möta dig) i kalendern och i e-postbekräftelser och påminnelser till relevant personal. Till exempel är det som visas i bokningar för en avtalad tid med en kund som innehåller 15 minuters tids period.

Observera att själva händelsen (till vänster i bilden nedan) visar ljusare skuggning för buffertstorlek och mörkare skuggning för den faktiska avtalade tiden. Den avtalade tiden ringer (som öppnas när du väljer händelsen) specifikt visar att den avtalade tiden är från 9:00AM till 10:00AM med Katie Jordanien och inkluderar 15 minuters bufferts tid före den avtalade tiden och 0 minuter efter den avtalade tiden. Bekräftelser och påminnelser till Personalen på liknande sätt refererar till en speciell buffert och avtalad tid medan kunden bara får bekräftelse och påminnelser som hänvisar till en 9:00AM till 10:00AM avtalad tid.

   ![Bild av den avtalade tiden med den tidsbuffertstorlek som visas](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Buffertstorlek och tillgänglighet

Kunderna ser inte direkt och kan inte ändra de buffertlängd du angett. Men för att buffra tid används för att beräkna den totala tjänste längden kommer kunderna att se dig och din relevanta personal som Bokad under både buffert och återkommande avtalad tid. Kunderna ser också tillgänglighet för dig och din personal om det finns tillräckligt med tid för både den avtalade tiden och dess buffertlängd.

I ett exempel krävs ett ledigt tids block om minst 1 timme och 15 minuter för en avtalad tid i en timme med en buffertlängd på 15 minuter. En avtalad tid för den här tjänsten skulle därför fylla ett 75-minuters tid i kalendern och behöver 75 minuters tillgänglighet till bok utan konflikt.
