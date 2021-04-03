---
title: Händelsetidslinje med hantering av hot och hot
description: Händelsetidslinje är en nyhetsfeed för risker som hjälper dig att tolka hur risker introduceras i organisationen och vilka åtgärder som har åtgärdats för att minska den.
keywords: händelsetidslinje, tidslinje för mdatp-händelse, mdatp-händelsetidslinje, hot och sårbarhetshantering, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90a124f9b0bf9ef775141e359224fde566c61c8d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501201"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a>Händelsetidslinje – hantering av hot och hot

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Händelsetidslinje är en nyhetsfeed som hjälper dig att tolka hur risker införs i organisationen genom nya säkerhetsproblem eller sårbarheter. Du kan visa händelser som kan påverka organisationens risker. Du kan till exempel hitta nya säkerhetsproblem som har introducerats, säkerhetsproblem som blev sårbarheter, sårbarheter som lagts till i en sårbarhetssats och mycket mer.

Händelsetidslinje berättar även om [exponeringsresultatet](tvm-exposure-score.md) och [Microsoft Secure Score för](tvm-microsoft-secure-score-devices.md) enheter så att du kan fastställa orsaken till stora förändringar. Händelser kan påverka dina enheter eller poäng för enheter. Minska exponeringen genom att åtgärda vad som behöver åtgärdas baserat på de prioriterade [säkerhetsrekommendationerna.](tvm-security-recommendation.md)

>[!TIP]
>E-postmeddelanden om nya sårbarhetshändelser finns i [Konfigurera e-postaviseringar om säkerhetsrisk i Microsoft Defender för slutpunkt](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-event-timeline-page"></a>Gå till sidan Händelsetidslinje

Det finns också tre inledningen till instrumentpanelen för hot [och sårbarhetshantering:](tvm-dashboard-insights.md)

- **Styrkort för exponering för** organisation: Hovra över händelseträffarna i diagrammet "Exponeringsresultat över tid" och välj "Visa alla händelser från den här dagen". Händelserna motsvarar säkerhetsproblem med programvara.
- **Microsoft Secure Score för enheter:** Hovra över händelseträffarna i diagrammet "Poäng för enheter över tid" och välj "Visa alla händelser från den här dagen". Händelserna representerar nya konfigurationsutvärderingar.
- **De viktigaste** evenemangskorten: Välj "Visa mer" längst ned i den översta händelsetabellen. Kortet visar de tre mest effektfulla händelserna under de senaste sju dagarna. Effektfulla händelser kan inkludera om händelsen påverkar ett stort antal enheter eller om det är ett kritiskt problem.

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a>Exponeringsresultat och Microsoft Secure Score för enheter

I instrumentpanelen för hantering av hot och risker hovrar du över diagrammet med exponeringsresultat för att visa de viktigaste säkerhetshändelserna för programvara från den dagen som påverkade dina enheter. Hovra över diagrammet Microsoft Secure Score för enheter för att visa nya säkerhetskonfigurationsutvärderingar som påverkar resultatet.

Om det inte finns några händelser som påverkar dina enheter eller ditt poängresultat för enheter visas ingen.

![Hovra över ](images/tvm-event-timeline-exposure-score350.png) 
 ![ exponeringsresultat för Microsoft Secure Score för enheter – hovra](images/tvm-event-timeline-device-hover360.png)

### <a name="drill-down-to-events-from-that-day"></a>Öka detalj detalj detalj för händelser från den dagen

Om **du väljer Visa alla händelser från** den här dagen kommer du till sidan Händelsetidslinje med ett anpassat datumintervall för den dagen.

![Händelsetidslinje valt anpassat datumintervall](images/tvm-event-timeline-drilldown.png)

Välj **Anpassat område** om du vill ändra datumintervallet till ett annat anpassat, eller ett förinställt tidsperiodintervall.

![Datumintervallsalternativ för händelsetidslinje](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a>Översikt över händelsetidslinje

På sidan Händelsetidslinje kan du visa all nödvändig information som är relaterad till en händelse. 

Funktioner:

- Anpassa kolumner
- Filtrera efter händelsetyp eller procent av påverkade enheter
- Visa 30, 50 eller 100 objekt per sida

De två stora siffrorna längst upp på sidan visar antalet nya säkerhetsproblem och sårbarheter, inte händelser. Vissa händelser kan ha flera säkerhetsproblem, och vissa säkerhetsproblem kan ha flera händelser.

![Sidan Händelsetidslinje](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a>Kolumner

- **Datum:** månad, dag, år
- **Händelse**: effektfull händelse, inklusive komponent, typ och antal påverkade enheter
- **Relaterad komponent:** programvara
- **Ursprungligen påverkade enheter:** antalet och procentandelen påverkade enheter när den här händelsen ursprungligen inträffade. Du kan också filtrera efter procentandelen ursprungligen påverkade enheter, av ditt totala antal enheter.
- **Enheter som för närvarande påverkas**: aktuellt antal och procentandel av enheter som den här händelsen för närvarande påverkar. Du hittar fältet genom att välja **Anpassa kolumner.**
- **Typer**: speglar tidsstämplade händelser som påverkar poängen. De kan filtreras.
    - Sårbarhet tillagd i en sårbarhetssats
    - Sårbarhet har verifierats
    - Ny offentlig sårbarhet
    - Ny sårbarhet
    - Ny konfigurationsutvärdering
- **Poängtrend**: trend för exponeringsresultat

### <a name="icons"></a>Ikoner

Följande ikoner visas bredvid händelser:

- ![felikon](images/tvm-black-bug-icon.png) Ny offentlig sårbarhet
- ![varningsikon för rapport](images/report-warning-icon.png) Ny sårbarhet publicerades
- ![exploit kit](images/bug-lightning-icon2.png) Sårbarhet som hittas i sårbarhetskit
- ![felikon med varningsikon](images/bug-caution-icon2.png) Sårbarhet verifierad

### <a name="drill-down-to-a-specific-event"></a>Öka detalj detalj för en viss händelse

När du har valt en händelse visas en utfäll kant med en lista över information och aktuella CV:n som påverkar dina enheter. Du kan visa fler CV:er eller visa den relaterade rekommendationen.

Pilen under "poängtrend" hjälper dig att avgöra om händelsen eventuellt höjer eller sänker exponeringsresultatet för organisationen. Högre exponeringsresultat innebär att enheter är mer sårbara för användning.

![Utfällning av händelsetidslinje](images/tvm-event-timeline-flyout500.png)

Därifrån väljer du Gå **till relaterad säkerhetsrekommendationer,** se rekommendationen som handlar om den nya programsäkerhetsproblemen på [sidan med säkerhetsrekommendationer.](tvm-security-recommendation.md) När du har läst beskrivningen och sårbarhetsinformationen i säkerhetsrekommendationern kan du skicka en begäran om åtgärder och spåra begäran på [sidan För att åtgärda.](tvm-remediation.md)  

## <a name="view-event-timelines-in-software-pages"></a>Visa tidslinjer för händelser på programvarusidor

Om du vill öppna en programvarusida väljer du en händelse > väljer det hyperlänkade programvarunamnet (till exempel Visual Studio 2017) i avsnittet "Related component" i den utfällbar menyn. [Läs mer om programvarusidor](tvm-software-inventory.md#software-pages)

En hel sida med all information om en viss programvara visas. Håll muspekaren över diagrammet för att se tidslinjen för händelser för den specifika programvaran.

![Programvarusida med ett tidslinjediagram för en händelse](images/tvm-event-timeline-software2.png)

Gå till fliken händelsetidslinje för att visa alla händelser som hör till den programvaran. Du kan även se säkerhetsrekommendationer, identifierade säkerhetsproblem, installerade enheter och versionsdistribution.

![Programvarusida med en tidslinjeflik för en händelse](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Instrumentpanelen](tvm-dashboard-insights.md)
- [Exponeringsvärde](tvm-exposure-score.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Åtgärda säkerhetsproblem](tvm-remediation.md)
- [Programvaruinventering](tvm-software-inventory.md)

