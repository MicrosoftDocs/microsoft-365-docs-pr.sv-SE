---
title: API:er för Microsoft 365 Defender-incidenter och resurstypen för incidenter
description: Läs mer om metoder och egenskaper för resurstypen Incident i Microsoft 365 Defender
keywords: incident, incidenter, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928360"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API för Microsoft 365 Defender-incidenter och resurstypen för incidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

En [incident](incidents-overview.md) är en samling relaterade aviseringar som hjälper till att beskriva en attack. Händelser från olika enheter i organisationen aggregeras automatiskt av Microsoft 365 Defender. Du kan använda API för incidenter för att programmässigt få åtkomst till organisationens incidenter och relaterade aviseringar.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Du kan begära upp till 50 samtal per minut eller 1 500 samtal per timme. Varje metod har också egna kvoter. Mer information om metodspecifika kvoter finns i respektive artikel för den metod du vill använda.

En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas eller `429` med tilldelad körningstid. Svarstexten innehåller tiden tills kvoten du har nått återställs.

## <a name="permissions"></a>Behörigheter

Api för incidenter kräver olika typer av behörigheter för var och en av dess metoder. Mer information om behörigheter som krävs finns i respektive metods artikel.

## <a name="methods"></a>Metoder

Metod | Returtyp | Beskrivning
-|-|-
[Lista incidenter](api-list-incidents.md) | [Incidentlista](api-incident.md) | Skapa en lista över incidenter.
[Uppdatera incident](api-update-incidents.md) | [Incident](api-incident.md) | Uppdatera en specifik händelse.

## <a name="request-body-response-and-examples"></a>Begäran om brödtext, svar och exempel

I respektive metodartiklar finns mer information om hur du skapar en begäran eller parsar ett svar och praktiska exempel.

## <a name="common-properties"></a>Vanliga egenskaper

Egenskap | Type (Typ) | Beskrivning
-|-|-
incidentId | long | Unikt ID för incidenter.
redirectIncidentId | nullable long | Det incident-ID som den aktuella incidenten kopplades till.
incidentName | sträng | Namnet på incidenten.
createdTime | DateTimeOffset | Datum och tid (i UTC) händelsen skapades.
lastUpdateTime | DateTimeOffset | Datum och tid (i UTC) incidenten uppdaterades senast.
assignedTo | sträng | Ägaren av incidenten.
allvarlighetsgrad | Uppräkning | Incidentens allvarlighetsgrad. Möjliga värden är: ```UnSpecified``` ```Informational``` , , och ```Low``` ```Medium``` ```High``` .
status | Uppräkning | Anger den aktuella statusen för incidenten. Möjliga värden är: ```Active``` ```Resolved``` och ```Redirected``` .
klassificering | Uppräkning | Specifikation för incidenten. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determination | Uppräkning | Anger incidentens avgörande. Möjliga värden är: ```NotAvailable``` , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
taggar | stränglista | Lista över incidenttaggar.
aviseringar | Aviseringslista | Lista med relaterade aviseringar. Se exempel i [API-dokumentationen för](api-list-incidents.md) listincidenter.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över API:er för Microsoft 365 Defender](api-overview.md)
- [Översikt över incidenter](incidents-overview.md)
- [API för listincidenter](api-list-incidents.md)
- [API för uppdateringshändelse](api-update-incidents.md)
