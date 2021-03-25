---
title: machineAction-resurstyp
description: Läs mer om metoder och egenskaper för resurstypen MachineAction i Microsoft Defender för Slutpunkt.
keywords: apis, API som stöds, skaffa, maskinåtgärd, senaste
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187391"
---
# <a name="machineaction-resource-type"></a>Resurstypen MachineAction

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Mer information finns i [Svarsåtgärder](respond-machine-alerts.md). 

| Metod                                                            | Returtyp                        | Beskrivning                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [List MachineActions](get-machineactions-collection.md)           | [Maskinåtgärd](machineaction.md) | Enheter [inom List Machine Action.](machineaction.md)           |
| [Get MachineAction](get-machineaction-object.md)                  | [Maskinåtgärd](machineaction.md) | Skaffa en enda [enhet med datoråtgärder.](machineaction.md)     |
| [Paket för insamling av undersökning](collect-investigation-package.md) | [Maskinåtgärd](machineaction.md) | Samla in undersökningspaket från en [dator.](machine.md) |
| [Get investigation package SAS URI](get-package-sas-uri.md)       | [Maskinåtgärd](machineaction.md) | Hämta URI för att hämta undersökningspaketet.          |
| [Isolera datorn](isolate-machine.md)                             | [Maskinåtgärd](machineaction.md) | Isolera [datorn](machine.md) från nätverket.                 |
| [Släpp datorn från isolation](unisolate-machine.md)            | [Maskinåtgärd](machineaction.md) | Släpp [datorn](machine.md) från isolationet.               |
| [Begränsa appkörning](restrict-code-execution.md)              | [Maskinåtgärd](machineaction.md) | Begränsa programkörning.                             |
| [Ta bort appbegränsning](unrestrict-code-execution.md)            | [Maskinåtgärd](machineaction.md) | Ta bort begränsning för programkörning.                   |
| [Kör antivirussökning](run-av-scan.md)                              | [Maskinåtgärd](machineaction.md) | Kör en AV-sökning med Windows Defender (om tillämpligt).    |
| [Offboard-dator](offboard-machine-api.md)                       | [Maskinåtgärd](machineaction.md) | [Offboard-dator](machine.md) från Microsoft Defender för Endpoint. |
| [Stoppa och sätt filen i karantän](stop-and-quarantine-file.md)           | [Maskinåtgärd](machineaction.md) | Stoppa körningen av en fil på en dator och ta bort den.        |

<br>

## <a name="properties"></a>Egenskaper

| Egenskap            | Skriv           | Beskrivning                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Identiteten för [datoråtgärden.](machineaction.md)                                                                                                                                                     |
| skriv                | Uppräkning           | Typ av åtgärd. Möjliga värden är: "RunAntiVirusTour", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" och "UnrestrictCodeExecution" |
| omfattning               | sträng         | Åtgärdens omfattning. "Fullständig" eller "Selektiv" för avgränsning, "Snabb" eller "Fullständig" för virussökning.                                                                                                   |
| beställare           | Sträng         | Identiteten för den person som utförde åtgärden.                                                                                                                                                               |
| requestorComment    | Sträng         | Kommentar som skrevs när åtgärden utfärdades.                                                                                                                                                              |
| status              | Uppräkning           | Aktuell status för kommandot. Möjliga värden är: "Väntande", "InProgress", "Lyckades", "Misslyckades", "TimeOut" och "Avbruten".                                                                                 |
| machineId           | Sträng         | ID för [den](machine.md) dator där åtgärden kördes.                                                                                                                                              |
| machineId           | Sträng         | Namnet på [den](machine.md) dator där åtgärden kördes.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | Datum och tid då åtgärden skapades.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | Datum och tid då åtgärdsstatus uppdaterades senast.                                                                                                                                                     |
| relatedFileInfo     | Klass          | Innehåller två egenskaper. sträng ```fileIdentifier``` , Uppräkning ```fileIdentifierType``` med möjliga värden: "Sha1", "Sha256" och "Md5".                                                                         |


## <a name="json-representation"></a>Json-representation

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
