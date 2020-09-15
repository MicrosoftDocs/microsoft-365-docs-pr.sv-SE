---
title: Resurs typ för incidenten i Microsoft Threat Protection API
description: Lär dig mer om metoderna och egenskaperna för resurs typen incident i Microsoft Threat Protection
keywords: incident, incidenter, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650582"
---
# <a name="incident-resource-type"></a>Resurs typ för incident

**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

## <a name="methods"></a>Verifieringsmetoder

Metod |Returtyp |Beskrivning
:---|:---|:---
[List händelser](api-list-incidents.md) | [Incident](api-incident.md) lista | Få en lista över incidenter.
[Uppdatera incident](api-update-incidents.md) | [Händelse](api-incident.md) | Uppdatera specifik incident.


## <a name="properties"></a>Fjärråtkomstsegenskaper

Egenskap |    Type (Typ)    |    Beskrivning
:---|:---|:---
incidentId | tids | Unikt ID för incidenten.
redirectIncidentId | null-värde långa | Incident-ID för den aktuella incidenten slogs samman till.
incidentName | strängvärdet | Namnet på incidenten.
createdTime | DateTimeOffset | Datum och tid (i UTC) då incidenten skapades.
lastUpdateTime | DateTimeOffset | Datum och tid (i UTC) då incidenten senast uppdaterades.
Tilldelat | strängvärdet | Ägaren till incidenten.
allvarlighets grad | Enum | Allvarlighets grad för incidenten. Möjliga värden är: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` och ```High``` .
status | Enum | Anger den aktuella statusen för incidenten. Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .
nomenklatur | Enum | Specifikation av felet. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
bedömning | Enum | Anger hur incidenten ska visas. Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
taggen | sträng lista | Lista över incident koder.
larm | Aviserings lista | Lista med relaterade aviseringar. Se exemplen på API-dokumentation för [samtal](api-list-incidents.md) .