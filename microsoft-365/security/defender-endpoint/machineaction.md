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
ms.openlocfilehash: a3b017a9a05964c15411668787b035f1052c68cf
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878286"
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
| [Samla in undersökningspaket](collect-investigation-package.md) | [Maskinåtgärd](machineaction.md) | Samla in undersökningspaket från en [dator.](machine.md) |
| [Hämta undersökningspaket för SAS URI](get-package-sas-uri.md)       | [Maskinåtgärd](machineaction.md) | Hämta URI för att hämta undersökningspaketet.          |
| [Isolera maskin](isolate-machine.md)                             | [Maskinåtgärd](machineaction.md) | Isolera [datorn](machine.md) från nätverket.                 |
| [Släppa maskin för isolering](unisolate-machine.md)            | [Maskinåtgärd](machineaction.md) | Släpp [datorn](machine.md) från isolationet.               |
| [Begränsa körning av program](restrict-code-execution.md)              | [Maskinåtgärd](machineaction.md) | Begränsa programkörning.                             |
| [Ta bort programbegränsning](unrestrict-code-execution.md)            | [Maskinåtgärd](machineaction.md) | Ta bort begränsning för programkörning.                   |
| [Kör antivirusgenomsökning](run-av-scan.md)                              | [Maskinåtgärd](machineaction.md) | Kör en AV-sökning med Windows Defender (om tillämpligt).    |
| [Avregistrera maskin](offboard-machine-api.md)                       | [Maskinåtgärd](machineaction.md) | [Offboard-dator](machine.md) från Microsoft Defender för Endpoint. |
| [Stoppa och placera filen i karantän](stop-and-quarantine-file.md)           | [Maskinåtgärd](machineaction.md) | Stoppa körningen av en fil på en dator och ta bort den.        |
| [Kör livesvar](run-live-response.md)                     | [Maskinåtgärd](machineaction.md)  | Kör en sekvens av kommandon för livesvar på en enhet                       |
| [Få livesvarsresultat](get-live-response-result.md) | URL-entitet      | Hämtar nedladdningslänk för specifika livesvarskommandon med hjälp av indexet. |
|[Åtgärden Avbryt dator](cancel-machine-action.md)                                | [Maskinåtgärd](machineaction.md)  | Avbryta en åtgärd på den aktiva datorn.                                            |

<br>

## <a name="properties"></a>Egenskaper

| Egenskap            | Typ           | Beskrivning                                                                                                                                                                                                    |
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
