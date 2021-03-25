---
title: Get MachineAction object API
description: Lär dig hur du använder Get MachineAction API för att hämta en specifik maskinåtgärd med dess ID i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, machineaction-objekt
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200071"
---
# <a name="get-machineaction-api"></a>Skaffa machineAction API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hämtar specifik [maskinåtgärd genom](machineaction.md) dess ID.


## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.Read.All |  "Läs alla maskinprofiler"
Program |   Machine.ReadWrite.All | "Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.Read | "Läs maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)

## <a name="http-request"></a>HTTP-begäran
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200, OK-svarskod med en [datoråtgärdsentitet.](machineaction.md) Om maskinåtgärdsentitet med det angivna ID:t inte hittades – 404 Hittades inte.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

**Svar**

Här är ett exempel på svaret.


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
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
