---
title: Få svarsresultat i livesändning
description: Lär dig hur du hämtar ett specifikt resultat av livesvarskommandot efter indexet.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879785"
---
#  <a name="get-live-response-results"></a>Få svarsresultat i livesändning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning

Hämtar ett specifikt resultat för livesvarskommandot efter index.

## <a name="limitations"></a>Begränsningar

1.  Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)

| Behörighetstyp                    | Behörighet           | Visningsnamn för behörighet                   |
|------------------------------------|----------------------|-------------------------------------------|
| Program                        | Machine.LiveResponse | Köra livesvar på en viss dator |
| Delegerat (arbets- eller skolkonto) | Machine.LiveResponse | Köra livesvar på en viss dator |

## <a name="http-request"></a>HTTP-begäran

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Begäran om rubriker

| Namn      | Typ | Beskrivning               |
|---------------|----------|-------------------------------|
| Auktorisering | Sträng   | Bearer {token}. Obligatoriskt. |

## <a name="request-body"></a>Begärans brödtext

Tom

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200, returnerar OK-svarskod med objekt som innehåller länken till kommandot resultat i *värdeegenskapen.* Den här länken är giltig i 30 minuter och bör användas direkt för att ladda ned paketet till ett lokalt lagringsutrymme. En länk som har gått ut kan skapas på nytt av ett annat samtal och du behöver inte köra livesvar igen.

*Egenskaper för runscript-transkription:*

| Egenskap  | Beskrivning                       |
|---------------|---------------------------------------|
| Namn          | Namn på körd skript                  |
| exit_code     | Körd avslutningskod för skript             |
| script_output | Kör skriptstandardresultat       |
| script_error  | Standardfelresultat för skript |

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Svar**

Här är ett exempel på svaret.

HTTP/1.1 200 Ok

Innehållstyp: program/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Filinnehåll:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Relaterade ämnen

- [Skaffa API för maskinåtgärd](get-machineaction-object.md)
- [Åtgärden Avbryt dator](cancel-machine-action.md)
- [Kör livesvar](run-live-response.md) 
