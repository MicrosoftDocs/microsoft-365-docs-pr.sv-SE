---
title: Microsoft Defender Säkerhetscenter Instrumentpanel för säkerhetsåtgärder
description: Använd instrumentpanelen för att identifiera enheter som är riskerade, håll reda på status för tjänsten och se statistik och information om enheter och aviseringar.
keywords: instrumentpanel, aviseringar, ny, pågående, löst, risk, enheter för risk, rapportering, statistik, diagram, diagram, hälsa, active malware detections, hotkategori, kategorier, lösenords stjäla, utpressningstrojaner, sårbarhet, hot, låg allvarlighetsgrad, aktiv skadlig kod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072953"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Microsoft Defender Säkerhetscenter Instrumentpanel för säkerhetsåtgärder

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

Instrumentpanelen **för säkerhetsåtgärder** är den identifiering och åtgärd på slutpunkt funktionerna visas. Den ger en översikt över var identifieringar har setts och markerar var svarsåtgärder krävs. 

Instrumentpanelen visar en ögonblicksbild av:

- Aktiva aviseringar
- Enheter som är riskfyllda
- Sensorhälsa
- Tjänstens hälsa
- Daglig rapportering om enheter
- Aktiva automatiserade undersökningar
- Automatisera undersökningar – statistik
- Användare i riskabelt-för-
- Misstänkta aktiviteter


![Bild av instrumentpanelen för säkerhetsåtgärder](images/atp-sec-ops-dashboard.png)

Du kan utforska och undersöka aviseringar och enheter för att snabbt avgöra om, var och när misstänkta aktiviteter inträffade i nätverket för att hjälpa dig att förstå kontexten de visades i.

Från **instrumentpanelen för säkerhetsåtgärder** ser du aggregerade händelser för att underlätta identifiering av viktiga händelser eller beteenden på en enhet. Du kan också öka detaljnivån för detaljerade händelser och indikatorer på låg nivå.

Den har också klickbara paneler som ger visuella ledtrådar om organisationens allmänna status. Varje panel öppnar en detaljerad vy av motsvarande översikt.

## <a name="active-alerts"></a>Aktiva aviseringar
Du kan visa det totala antalet aktiva aviseringar från de senaste 30 dagarna i nätverket från panelen. Aviseringar grupperas i **Nytt** och **Pågående**.

![Klicka på varje sektor eller allvarlighetsgrad för att se en lista med aviseringar från de senaste 30 dagarna](images/active-alerts-tile.png)

Varje grupp kategoriseras ytterligare i motsvarande allvarlighetsnivå för aviseringar. Klicka på antalet aviseringar i varje aviseringsring om du vill se en sorterad vy av den kategorins kö **(Ny** eller **Pågår).**

Mer information finns i Översikt [över aviseringar.](alerts-queue.md)

Varje rad innehåller en kategori med en aviserings allvarlighetsgrad och en kort beskrivning av aviseringen. Du kan klicka på en avisering om du vill se den detaljerade vyn. Mer information finns i Undersök [Microsoft Defender för slutpunktsaviseringar och](investigate-alerts.md) [översikten Aviseringar.](alerts-queue.md)


## <a name="devices-at-risk"></a>Enheter som är riskfyllda
På panelen visas en lista över enheter med det högsta antalet aktiva aviseringar. Det totala antalet aviseringar för varje enhet visas i en cirkel bredvid enhetens namn och kategoriseras ytterligare efter allvarlighetsnivå längst ut i panelen (hovra över varje allvarlighetsfält om du vill se dess etikett).

![På panelen Enheter vid risk visas en lista över enheter med det högsta antalet aviseringar och en uppdelning av varningarnas allvarlighetsgrad](images/devices-at-risk-tile.png)

Klicka på enhetens namn om du vill se information om den enheten. Mer information finns i Undersöka [enheter i listan Microsoft Defender för slutpunktsenheter.](investigate-machines.md)

Du kan också klicka **på Listan** Enheter högst upp på panelen för att gå direkt till listan Enheter **,** sorterad efter antalet aktiva aviseringar. Mer information finns i Undersöka [enheter i listan Microsoft Defender för slutpunktsenheter.](investigate-machines.md)

## <a name="devices-with-sensor-issues"></a>Enheter med sensorproblem
Panelen **Enheter med sensorproblem** ger information om den enskilda enhetens möjlighet att ge sensordata till Microsoft Defender för slutpunktstjänsten. Den rapporterar hur många enheter som kräver uppmärksamhet och hjälper dig att identifiera problematiska enheter.

![Panelen enheter med sensorproblem](images/atp-tile-sensor-health.png)

Det finns två statusindikatorer med information om antalet enheter som inte rapporterar korrekt till tjänsten:
- **Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Microsoft Defender för Slutpunkt-tjänsten och kan ha konfigurationsfel som behöver korrigeras.
- **Inaktiva** – Enheter som har slutat rapportera till Microsoft Defender för slutpunktstjänsten under mer än sju dagar den senaste månaden.

När du klickar på någon av grupperna dirigeras du till listan över enheter, filtrerade enligt ditt val. Mer information finns i Kontrollera [sensortillståndet](check-sensor-status.md) och [Undersöka enheter.](investigate-machines.md)

## <a name="service-health"></a>Tjänstens hälsa
Panelen **Tjänstens** hälsa informerar dig om tjänsten är aktiv eller om det är problem.

![Panelen Tjänstens hälsa visar en övergripande indikator på tjänsten](images/status-tile.png)

Mer information om tjänstens hälsa finns i [Kontrollera tjänstens hälsa för Microsoft Defender.](service-status.md)


## <a name="daily-devices-reporting"></a>Daglig rapportering om enheter
På **panelen för daglig rapportering** visas ett stapeldiagram som representerar antalet enheter som rapporterar dagligen under de senaste 30 dagarna. Hovra över enskilda staplar i diagrammet för att se det exakta antalet enheter som rapporterar varje dag.

![Bild på rapportpanel för dagliga enheter](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a>Aktiva automatiserade undersökningar
Du kan visa det totala antalet automatiserade undersökningar från de senaste 30 dagarna i nätverket från panelen för **automatiska aktiv undersökningar.** Undersökningar grupperas i **Väntande åtgärd**, **Väntar på enhet** och **Körs**.

![Drift av aktiva automatiserade undersökningar](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a>Automatisera undersökningar – statistik
I panelen visas statistik som är relaterad till automatiserade undersökningar de senaste sju dagarna. Den visar antalet undersökningar som slutförts, antalet slutförda undersökningar, den genomsnittliga väntande tiden det tar för en undersökning att initieras, den genomsnittliga tiden det tar att åtgärda en avisering, antalet aviseringar som undersökts och antalet timmar av automatisering som sparats från en vanlig manuell undersökning. 

![Bild av automatiserad statistik för undersökningar](images/atp-automated-investigations-statistics.png)

Du kan klicka på  **Automatiserade** undersökningar, **åtgärdade** undersökningar och aviseringar som har **undersökts** för att navigera till sidan Undersökningar, filtrerad efter lämplig kategori. På så sätt kan du se en detaljerad uppdelning av undersökningar i sammanhanget.

## <a name="users-at-risk"></a>Användare i riskabelt-för-
Panelen visar en lista över användarkonton med de mest aktiva aviseringarna och antalet aviseringar som visas på höga, medelstora eller låga aviseringar. 

![Användarkonton på riskpanelen visar en lista över användarkonton med det högsta antalet aviseringar och en uppdelning av varningarnas allvarlighetsgrad](images/atp-users-at-risk.png)

Klicka på användarkontot om du vill se mer information om användarkontot. Mer information finns i [Undersöka ett användarkonto.](investigate-user.md)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>Relaterade ämnen
- [Förstå Microsoft Defender för Slutpunktsportalen](use.md)
- [Portalöversikt](portal-overview.md)
- [Visa instrumentpanelen för & Sårbarhetshantering](tvm-dashboard-insights.md)
- [Visa instrumentpanelen för hotanalyser och vidta rekommenderade åtgärder](threat-analytics.md)
