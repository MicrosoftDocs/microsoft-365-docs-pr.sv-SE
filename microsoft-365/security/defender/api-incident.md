---
title: Microsoft 365 Api:er för Defender-incidenter och resurstypen för incidenter
description: Läs mer om metoderna och egenskaperna för resurstypen Incidenter i Microsoft 365 Defender
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888439"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defender-incident-API:t och resurstypen för incidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

En [incident](incidents-overview.md) är en samling relaterade aviseringar som beskriver en attack. Händelser från olika enheter i organisationen aggregeras automatiskt av Microsoft 365 Defender. Du kan använda incident-API:t för att programmässigt få åtkomst till organisationens incidenter och relaterade aviseringar.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Du kan begära upp till 50 samtal per minut eller 1 500 samtal per timme. Varje metod har också egna kvoter. Mer information om metodspecifika kvoter finns i respektive artikel för den metod du vill använda.

En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid. Svarstexten tar med tiden tills kvoten du har nått återställs.

## <a name="permissions"></a>Behörigheter

För incident-API:t krävs olika typer av behörigheter för var och en av dess metoder. Mer information om obligatoriska behörigheter finns i respektive metods artikel.

## <a name="methods"></a>Metoder

Metod | Returtyp | Beskrivning
-|-|-
[Lista incidenter](api-list-incidents.md) | [Incidentlista](api-incident.md) | Få en lista över alla incidenter.
[Uppdatera incident](api-update-incidents.md) | [Incident](api-incident.md) | Uppdatera en specifik händelse.
[Hämta incident](api-get-incident.md) | [Incident](api-incident.md) | Få en enda incident.

## <a name="request-body-response-and-examples"></a>Begärans brödtext, svar och exempel

Mer information om hur du skapar en begäran eller parsar ett svar samt praktiska exempel finns i respektive metodartiklar.

## <a name="common-properties"></a>Gemensamma egenskaper

Egenskap | Typ | Beskrivning
-|-|-
incidentId | long | Unikt ID för incidenter.
redirectIncidentId | nullbar long | Det incident-ID som den aktuella incidenten kopplades till.
incidentName | sträng | Namnet på incidenten.
createdTime | DateTimeOffset | Datum och tid (i UTC) som incidenten skapades.
lastUpdateTime | DateTimeOffset | Datum och tid (i UTC) som incidenten uppdaterades senast.
assignedTo | sträng | Ägaren till händelsen.
allvarlighetsgrad | Uppräkning | Incidentens allvarlighetsgrad. Möjliga värden är: ```UnSpecified``` , , , och ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Uppräkning | Anger incidentens aktuella status. Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .
klassificering | Uppräkning | Specifikation för incidenten. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determination | Uppräkning | Anger incidentens avgörande. Möjliga värden är: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
taggar | stränglista | Lista över incidenttaggar.
kommentarer | Lista över incidentkommentarer | Incidentkommentarsobjekt innehåller: kommentarssträng, createdBy-sträng och createTime-datumtid.
aviseringar | Aviseringslista | Lista med relaterade aviseringar. Se exempel i [dokumentationen för API för listincidenter.](api-list-incidents.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Översikt över Defender-API:er](api-overview.md)
- [Översikt över incidenter](incidents-overview.md)
- [API för listincidenter](api-list-incidents.md)
- [Api för uppdatering av incident](api-update-incidents.md)
