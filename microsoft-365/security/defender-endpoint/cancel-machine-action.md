---
title: Api:t Avbryt datoråtgärd
description: Lär dig hur du avbryter en maskinåtgärd som redan startats
keywords: apis, graph api,
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
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879802"
---
#   <a name="cancel-machine-action-api"></a>Api:t Avbryt datoråtgärd 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning

Avbryta en maskinåtgärd som redan startats och som ännu inte är i slutänden (slutförd, avbruten, misslyckades).

## <a name="limitations"></a>Begränsningar

1.  Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)

|     Behörighetstyp     |     Behörighet     |    Visningsnamn för behörighet     |
|-|-|-|
|    <br>Program    |    <br>Machine.CollectForensic<br>   Dator.Isolera   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Samla in en forensisk information   <br>Isolera datorn<br>Begränsa kodkörning<br>  Skanna dator<br>  Offboard-dator<br>   Stoppa och sätta i karantän<br>   Köra livesvar på en viss dator    |
|    <br>Delegerat (arbets- eller skolkonto)    |    Machine.CollectForensic<br>   Dator.Isolera    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Samla in en forensisk information<br>   Isolera datorn<br>  Begränsa kodkörning<br> Skanna dator<br>Offboard-dator<br> Stoppa och sätta i karantän<br> Köra livesvar på en viss dator    |


## <a name="http-request"></a>HTTP-begäran

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Begäran om rubriker

| Namn      | Typ | Beskrivning                 |
|---------------|----------|---------------------------------|
| Auktorisering | Sträng   | Bearer {token}. Obligatoriskt.   |
| Innehållstyp  | sträng   | application/json. Obligatoriskt. |

## <a name="request-body"></a>Begärans brödtext

| Parameter | Typ | Beskrivning                        |
|---------------|----------|----------------------------------------|
| Kommentar       | Sträng   | Kommentar som ska kopplas till annulleringsåtgärden.  |

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200, OK-svarskod med en datoråtgärdsentitet. Om maskinåtgärdsentitet med det angivna ID:t inte hittades – 404 Hittades inte.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Relaterat ämne

- [Skaffa API för maskinåtgärd](get-machineaction-object.md)