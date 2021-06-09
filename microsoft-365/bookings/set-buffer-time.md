---
title: Ställa in tidsbuffert i Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Ställ in tidsbuffert före eller efter en avtalad tid i Microsoft Bookings så att det går att rensa eller återställa utrustning.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962353"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Ställa in tidsbuffert i Microsoft Bookings

Vissa av dina avtalade tider kan kräva tid före eller efter mötet med kunden för att konfigurera, rensa och återställa rum och utrustning. Om du är på resande fot mellan olika kundbokningar kan du behöva tid och se till att du och din grupp kan resa mellan avtalade tider utan att kunden får vänta.

Du kan ange tidsbuffert innan avtalade tider börjar, när avtalade tider är slut eller både och för att ge personalen den extra tid de behöver för att förbereda sig för nästa avtalade tid.

## <a name="set-buffer-time-defaults"></a>Ange standardvärden för tidsbuffert

Standardvärden för tidsbuffert anges **på sidan Tjänstinformation** i Bookings. Precis som alla standardinställningar för tjänster på den här sidan kan du redigera standardinställningarna för en bokning så att de uppfyller vissa kundbehov.

Inställningen för tidsbuffert hittar du strax under **Standardvaraktighetsväljare** på **sidan Tjänstinformation.** Innan den kan anges för en viss tjänst måste du aktivera inställningen för tidsbuffert genom att välja växlingsknappen för tidsbuffert. Det här **gör**  att listrutan Före och Efter visas, som används för att välja standardtid för före och efter varje bokning, som visas här:

   ![Bild på Bookings med tidsbuffert aktiverad](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tidsbuffert och tidsinställning för avtalad tid

För att undvika förvirring vad gäller när kunder förväntar sig att träffa dig kan Bookings visa tidsbuffert och faktisk tid för avtalade tider (den tid kunderna förväntar sig att träffa dig) i kalendern och i e-postbekräftelser och påminnelser till relevant personal. Nedan visas till exempel vad du skulle se i Bookings för en avtalad tid med en kund som innehåller 15 minuter tids tidsbuffert för avtalad tid.

Observera att själva händelsen (till vänster i bilden nedan) visar en ljusare skuggning för bufferttiden och en mörkare skuggning för den faktiska avtalade tiden för kunden. Den avtalade tidens uppringning (som öppnas när du markerar händelsen) visar specifikt att den avtalade tiden är från 09:00 till 10:00 med Katie Jordan och innehåller 15 minuters tidsbuffert före den avtalade tiden och 0 minuter efter den avtalade tiden. Bekräftelser och påminnelser till personal refererar på liknande sätt till specifik buffert- och avtalad tid medan kunden bara får bekräftelser och påminnelser som refererar till en tid mellan 21:00 och 10:00.

   ![Bild på utringning av avtalad tid i Bookings med tidsbuffert](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tidsbuffert och tillgänglighet

Kunderna kan inte direkt se och kan inte ändra de tidsbuffert du anger. Eftersom tidsbuffert används för att beräkna den totala tjänstelängden ser kunderna dig och din relevanta personal som bokade under både buffert- och vanliga tider för avtalade tider. Kunderna ser också bara tillgängligheten för dig och din personal om det finns tillräckligt med tid för både den avtalade tiden och dess tidsbuffert.

En tid på en timme med en tidsbuffert på 15 minuter kräver till exempel ett tillgängligt tidsblock på minst 1 timme och 15 minuter. En avtalad tid för den här tjänsten fyller därför ett 75 minuter lång tidsblock i kalendern och behöver 75 minuters tillgänglighet för att boka utan konflikt.
