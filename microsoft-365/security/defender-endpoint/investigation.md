---
title: Resurstyp för undersökning
description: Entitet för Microsoft Defender ATP-undersökning.
keywords: apis, graph api, api som stöds, skaffa, aviseringar, undersökningar
search.product: eADQiWindows 10XVcnh
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
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187355"
---
# <a name="investigation-resource-type"></a>Resurstyp för undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Representerar en automatiserad undersökningsentitet i Defender för Slutpunkt.
<br> Mer information [finns i Översikt över](automated-investigations.md) automatiserade undersökningar.

## <a name="methods"></a>Metoder
Metod|Returtyp |Beskrivning
:---|:---|:---
[Listundersökningar](get-investigation-collection.md) | Samling för undersökning | Hämta undersökningssamling
[Få en enda undersökning](get-investigation-object.md) | Undersökningsentitet | Får en enda undersökningsentitet.
[Starta undersökning](initiate-autoir-investigation.md) | Undersökningsentitet | Startar undersökning på en enhet.


## <a name="properties"></a>Egenskaper
Egenskap |  Skriv    |   Beskrivning
:---|:---|:---
id | Sträng | Identiteten för undersökningsentitet. 
startTime | DateTime Nullable | Datum och tid då undersökningen skapades. 
endTime | DateTime Nullable | Datum och tid då undersökningen slutfördes. 
cancelledBy | Sträng | ID för den användare/det program som avbröt undersökningen. 
investigationState | Uppräkning | Den aktuella undersökningstillståndet. Möjliga värden är: "Okänt", "Avslutat", "SuccessfullyRemediated", 'SuppressedAlert', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetaljer | Sträng | Ytterligare information om undersökningstillståndet.
machineId | Sträng | ID för enheten där undersökningen utförs.
computerDnsName | Sträng | Namnet på enheten där undersökningen utförs.
triggeringAlertId | Sträng | ID för den varning som utlöste undersökningen.


## <a name="json-representation"></a>Json-representation

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
