---
title: Händelseflaggor i Microsoft Defender för slutpunktsenhetstid
description: Använd Microsoft Defender för händelseflaggor på slutpunktsenhetens tidslinje för att
keywords: Defender för slutpunktsenhetstidslinje, händelseflaggor
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165159"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Händelseflaggor i Microsoft Defender för slutpunktsenhetstid

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Med händelseflaggor i Defender för slutpunktsenhetens tidslinje får du hjälp att filtrera och ordna specifika händelser när du undersöker potentiella attacker.

Defender för Endpoint-enhetens tidslinje ger en kronologisk vy av händelserna och tillhörande aviseringar som observeras på en enhet. Den här listan med händelser ger full insyn i händelser, filer och IP-adresser som observerats på enheten. Listan kan ibland vara lång. Med händelseflaggor på enhetstidslinjen kan du hålla reda på händelser som kan vara relaterade. 

När du har gått igenom en tidslinje på en enhet kan du sortera, filtrera och exportera specifika händelser som du har flaggat.

När du navigerar på enhetens tidslinje kan du söka efter och filtrera efter specifika händelser. Du kan ange händelseflaggor genom att: 

- Markera de viktigaste händelserna 
- Markera händelser som kräver djupdykning 
- Skapa en tidslinje med ett rent intrång



## <a name="flag-an-event"></a>Flagga en händelse
1. Hitta den händelse som du vill flagga
2. Klicka på flaggikonen i kolumnen Flagga. 
![Bild av tidslinjeflaggan på enheten](images/device-flags.png)

## <a name="view-flagged-events"></a>Visa flaggade händelser  
1. Aktivera Flaggade **händelser** i avsnittet **Filter på tidslinjen.**
2. Klicka på **Använd**. Endast flaggade händelser visas.
Du kan tillämpa ytterligare filter genom att klicka på tidsstapeln. Då visas bara händelser före den flaggade händelsen.  
![Bild av enhetens tidslinjeflagga med filter på](images/device-flag-filter.png)
