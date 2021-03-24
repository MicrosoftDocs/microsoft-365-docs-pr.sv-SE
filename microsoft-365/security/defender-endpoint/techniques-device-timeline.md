---
title: Tekniker på enhetens tidslinje
description: Förstå enhetens tidslinje i Microsoft Defender för Slutpunkt
keywords: tidslinje, slutpunkt, MITRE, MITRE ATT&CK, tekniker, taktiker
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6e2c18bd3710e659b5f9887844bc92528da4607
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070138"
---
# <a name="techniques-in-the-device-timeline"></a>Tekniker på enhetens tidslinje


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


Du kan få mer insyn i en undersökning genom att analysera händelserna på en viss enhet. Välj först den enhet som är intressant i [listan Enheter](machines-view-overview.md). På enhetens sida kan du välja fliken **Tidslinje** för att visa alla händelser som inträffat på enheten.

## <a name="understand-techniques-in-the-timeline"></a>Förstå tekniker i tidslinjen

>[!IMPORTANT]
>Viss information handlar om en förhandsversion av en produkt i en offentlig förhandsversion som kan komma att ändras väsentligt innan den släpps till allmänheten. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

I Microsoft Defender för Slutpunkt **är Tekniker** ytterligare en datatyp i händelsetidslinjen. Tekniker ger mer insyn i aktiviteter som associeras [med MITRE ATT&CK-tekniker](https://attack.mitre.org/) eller undertekniker. 

Den här funktionen förenklar undersökningsupplevelsen genom att hjälpa analytiker att förstå de aktiviteter som observerats på en enhet. Analytiker kan sedan bestämma sig för att undersöka ytterligare.

För offentlig förhandsgranskning är Tekniker tillgängliga som standard och visas tillsammans med händelser när en enhets tidslinje visas. 

![Skärmbild av tekniker på tidslinjen på enheten](images/device-timeline-2.png)

Tekniker markeras i fetstil och visas med en blå ikon till vänster. Motsvarande MITRE ATT&CK-ID och tekniknamn visas också som taggar under Ytterligare information. 

Sök- och exportalternativ är också tillgängliga för tekniker.

## <a name="investigate-using-the-side-pane"></a>Undersöka användning av sidofönstret

Välj en teknik för att öppna motsvarande sidofönster. Här kan du se ytterligare information och insikter som relaterade ATT&CK-tekniker, taktiker och beskrivningar. 

Välj den specifika *attacktekniken* för att öppna den relaterade att&CK-tekniksidan där du kan hitta mer information om den.

Du kan kopiera information om en enhet när du ser en blå ikon till höger. Om du till exempel vill kopiera den relaterade filens SHA1 väljer du den blå sidikonen.

![Kopiera entitetsinformation](images/techniques-side-pane-clickable.png)

Du kan göra samma sak för kommandorader.

![Kopiera kommandorad](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a>Undersöka relaterade händelser

Om du [vill använda avancerad](advanced-hunting-overview.md) sökning för att hitta händelser relaterade till den valda tekniken väljer du Sök efter relaterade **händelser.** Det leder till sidan för avancerad sökning med en fråga för att hitta händelser som hör till tekniken.

![Leta efter relaterade händelser](images/techniques-hunt-for-related-events.png)

>[!NOTE]
>Vid sökning med **knappen Sök** efter relaterade händelser från sidofönstret Teknik visas alla händelser som hör till den identifierade tekniken, men själva tekniken ingår inte i frågeresultatet.


## <a name="customize-your-device-timeline"></a>Anpassa enhetens tidslinje

Längst upp till höger på enhetens tidslinje kan du välja ett datumintervall för att begränsa antalet händelser och tekniker på tidslinjen. 

Du kan anpassa vilka kolumner som ska visas. Du kan också filtrera efter flaggade händelser efter datatyp eller händelsegrupp.

### <a name="choose-columns-to-expose"></a>Välj kolumner att visa
Du kan välja vilka kolumner som ska visas i tidslinjen genom att välja **knappen Välj** kolumner.

![Anpassa kolumner](images/filter-customize-columns.png)

Därifrån kan du välja vilken informationsuppsättning som ska inkluderas.

### <a name="filter-to-view-techniques-or-events-only"></a>Filter för att endast visa tekniker eller händelser

Om du bara vill visa händelser eller tekniker väljer **du Filter** på enhetens tidslinje och väljer den datatyp du vill visa.

![Skärmbild av filter](images/device-timeline-filters.png)



## <a name="see-also"></a>Se även
- [Visa och ordna listan Enheter](machines-view-overview.md)
- [Händelseflaggor i Microsoft Defender för slutpunktsenhetstid](device-timeline-event-flag.md) 


 
