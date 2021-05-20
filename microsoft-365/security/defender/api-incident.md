---
title: Microsoft 365 Api:er för defenderincidenter och incidentresurstypen
description: Lär dig mer om metoderna och egenskaperna för resurstypen Incident i Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572591"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 API för defenderincidenter och incidentresurstypen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

En [incident](incidents-overview.md) är en samling relaterade aviseringar som hjälper till att beskriva en attack. Händelser från olika entiteter i organisationen aggregeras automatiskt av Microsoft 365 Defender. Du kan använda incident-API:et för att programmässigt komma åt organisationens incidenter och relaterade aviseringar.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resursallokering

Du kan begära upp till 50 samtal per minut eller 1500 samtal per timme. Varje metod har också sina egna kvoter. Mer information om metodspecifika kvoter finns i respektive artikel för den metod som du vill använda.

En `429` HTTP-svarskod anger att du har nått en kvot, antingen efter antal skickade begäranden eller efter tilldelad körtid. Svarstexten kommer att inkludera tiden tills kvoten du nådde återställs.

## <a name="permissions"></a>Behörigheter

Incident-API:et kräver olika typer av behörigheter för var och en av dess metoder. Mer information om nödvändiga behörigheter finns i respektive metods artikel.

## <a name="methods"></a>metoder

Metod | Returtyp | Beskrivning
-|-|-
[Lista incidenter](api-list-incidents.md) | [Incidentlista](api-incident.md) | Få en lista över incidenter.
[Uppdatera incident](api-update-incidents.md) | [händelse](api-incident.md) | Uppdatera en specifik incident.

## <a name="request-body-response-and-examples"></a>Begär brödtext, svar och exempel

Mer information om hur du konstruerar en begäran eller tolkning av ett svar finns i respektive metodartiklar och för praktiska exempel.

## <a name="common-properties"></a>Vanliga egenskaper

Egenskap | Typ | Beskrivning
-|-|-
incidentId | lång | Incident unikt ID.
omdirigeraIncidentId | nullable lång | Incident-ID:t som den aktuella incidenten kopplades till.
incidentName | sträng | Namnet på incidenten.
createdTime | DatumTimeOffset | Datum och tid (i UTC) incidenten skapades.
lastUpdateTime | DatumTimeOffset | Datum och tid (i UTC) incidenten uppdaterades senast.
tilldeladTill | sträng | Ägare av incidenten.
stränghet | Uppräkning | Incidentens allvar. Möjliga värden är: ```UnSpecified``` , , , och ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Uppräkning | Anger incidentens aktuella status. Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .
klassificering | Uppräkning | Specifikation av incidenten. Möjliga värden är: ```Unknown``` , ```FalsePositive``` ```TruePositive``` .
beslutsamhet | Uppräkning | Anger bestämningen av incidenten. Möjliga värden är: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
Taggar | stränglista | Lista över incidenttaggar.
Kommentarer | Lista över incidentkommentarer | Objektet Incidentkommentar innehåller: kommentarsträng, skapad av sträng och createTime-datumtid.
Varningar | Aviseringslista | Lista över relaterade aviseringar. Se exempel på [API-dokumentation för](api-list-incidents.md) listincidenter.

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Översikt över Defender API:er](api-overview.md)
- [Översikt över incidenter](incidents-overview.md)
- [API för listincidenter](api-list-incidents.md)
- [Uppdatera incident-API](api-update-incidents.md)
