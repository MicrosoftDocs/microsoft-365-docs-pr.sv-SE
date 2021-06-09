---
title: Undersöka Microsoft Defender för slutpunktsaviseringar
description: Använd alternativen för undersökning för att få information om aviseringar påverkar nätverket, vad de betyder och hur du kan lösa dem.
keywords: undersök, undersökning, enheter, enhet, aviseringar, instrumentpanel, IP-adress, fil, skicka, inskickade data, djupanalys, tidslinje, sökning, domän, URL, IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841096"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Undersöka aviseringar i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

Undersök aviseringar som påverkar nätverket, förstå vad de betyder och hur du löser dem.

Välj en avisering från aviseringskön för att gå till aviseringssidan. Den här vyn innehåller aviseringsrubriken, de berörda tillgångarna, informationsfönstret och aviseringsartikeln.

Från aviseringssidan börjar du din undersökning genom att välja de berörda tillgångarna eller någon av enheterna under trädvyn för aviseringsartikeln. Informationsfönstret fylls automatiskt i med ytterligare information om det du har markerat. Om du vill se vilken typ av information du kan visa här kan du läsa [Granska aviseringar i Microsoft Defender för slutpunkt.](/microsoft-365/security/defender-endpoint/review-alerts)

## <a name="investigate-using-the-alert-story"></a>Undersök användning av aviseringsartikeln

Information om aviseringsinformationen varför aviseringen utlöstes, relaterade händelser som inträffat före och efter, samt andra relaterade enheter.

Enheter är klickbara och alla enheter som inte är en avisering kan utökas med hjälp av expanderikonen på höger sida av enhetens kort. Enheten i fokus anges med ett blått band till vänster om enhetens kort, med varningen i fokus först.

Utöka enheterna för att få en snabb överblick över informationen. När du väljer en entitet växlas kontexten för informationsfönstret till den här enheten och du kan granska ytterligare information och hantera den enheten. Om *du markerar ...* till höger om entitetskortet visas alla åtgärder som är tillgängliga för den enheten. Samma åtgärder visas i informationsfönstret när entiteten är i fokus.

> [!NOTE]
> Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.

![Ett exempel på en aviseringsartikel med en varning i fokus och några expanderade kort](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>Vidta åtgärder från informationsfönstret

När du har valt en intresseenhet ändras informationsfönstret för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och erbjuder kontroller för att vidta åtgärder på den här enheten direkt från aviseringssidan. 

När du har undersökt klart går du tillbaka till den avisering  du började med, markerar aviseringens status som Löst och klassificerar den som antingen **Falsk avisering** eller **Sant-avisering.** Klassificera aviseringar hjälper till att finjustera den här funktionen för att ge mer sanna aviseringar och mindre falska aviseringar.

Om du klassificerar det som en verklig varning kan du också välja ett avgörande, som visas i bilden nedan.

![Ett avsnitt av informationsfönstret med en löst avisering och den expanderade listrutan för determination](images/alert-details-resolved-true.png)

Om du får en falsk avisering med ett affärsprogram skapar du en regel för att undvika den här typen av avisering i framtiden.

![åtgärder och klassificering i informationsfönstret med regeln markerad](images/alert-false-suppression-rule.png)

> [!TIP]
> Om du har problem som inte beskrivs ovan kan du använda knappen för 🙂 att ge feedback eller öppna ett supportärenden.


## <a name="related-topics"></a>Relaterade ämnen
- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka en fil som är kopplad till en Defender för slutpunktsavisering](investigate-files.md)
- [Undersök enheter i listan Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka en domän som är kopplad till en Defender för slutpunktsavisering](investigate-domain.md)
- [Undersöka ett användarkonto i Defender för Slutpunkt](investigate-user.md)


