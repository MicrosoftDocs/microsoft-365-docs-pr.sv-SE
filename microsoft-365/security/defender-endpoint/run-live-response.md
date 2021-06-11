---
title: Köra svarskommandon i livesändning på en enhet
description: Lär dig hur du kör en sekvens av kommandon för livesvar på en enhet.
keywords: apis, graph api, API som stöds, ladda upp till bibliotek
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879766"
---
#  <a name="run-live-response-commands-on-a-device"></a>Köra svarskommandon i livesändning på en enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning

Kör en sekvens av kommandon för livesvar på en enhet

## <a name="limitations"></a>Begränsningar

1.  Prisbegränsningar för detta API är 10 samtal per minut (ytterligare förfrågningar besvaras med HTTP 429).

2.  25 samtidiga sessioner (förfrågningar som överskrider begränsningsgränsen får svaret "429 – För många begäranden").

3.  Om datorn inte är tillgänglig köas sessionen i upp till 3 dagar.

4.  Tidsgränser för RunScript-kommandon efter 10 minuter.

5.  När ett live-svarskommando inte utför alla följda åtgärder.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)

| Behörighetstyp                    | Behörighet           | Visningsnamn för behörighet                   |
|------------------------------------|----------------------|-------------------------------------------|
| Program                        | Machine.LiveResponse | Köra livesvar på en viss dator |
| Delegerat (arbets- eller skolkonto) | Machine.LiveResponse | Köra livesvar på en viss dator |

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Begäran om rubriker

| Namn      | Typ | Beskrivning                 |
|---------------|----------|---------------------------------|
| Auktorisering | Sträng   | Bearer\<token>\. Obligatoriskt.   |
| Innehållstyp  | sträng   | application/json. Obligatoriskt. |

## <a name="request-body"></a>Begärans brödtext

| Parameter | Typ | Beskrivning                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Kommentar       | Sträng   | Kommentar som ska associeras med åtgärden.                                 |
| Kommandon      | Matris    | Kommandon som ska köras. Tillåtna värden är PutFile, RunScript och GetFile. |

Kommandon:

| Kommandotyp | Parametrar                                                                          | Beskrivning                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Nyckel: Filnamn  <br><br>  Värde: \<file name\>                                                                          | Lägger till en fil från biblioteket till enheten. Filer sparas i en arbetsmapp och tas bort när enheten startas om som standard.
| RunScript    | Nyckel: ScriptName<br>Värde: \<Script from library\> <br><br> Tangent: Args  <br> Värde: \<Script arguments\>                          | Kör ett skript från biblioteket på en enhet.    <br><br>  Parametern Args skickas till skriptet. <br><br> Tidsgränser efter 10 minuter.     
| GetFile      | Nyckel: Sökväg <br> Värde: \<File path\>                                                        | Samla in en fil från en enhet. Obs! Omslag i sökväg måste komma i väg.                                                                      |

## <a name="response"></a>Svar

-   Om det lyckas returnerar den här metoden 200, OK.
    Åtgärd entitet. Om ingen dator med det angivna ID:t hittades – 404 Hittades inte.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Svar**

Här är ett exempel på svaret.

```HTTP
HTTP/1.1 200 Ok
```

Innehållstyp: program/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Relaterade ämnen
- [Skaffa API för maskinåtgärd](get-machineaction-object.md)
- [Få livesvarsresultat](get-live-response-result.md)
- [Åtgärden Avbryt dator](cancel-machine-action.md)
