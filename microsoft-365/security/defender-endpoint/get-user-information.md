---
title: Hämta API för användarinformation
description: Lär dig hur du använder API:t för att hämta användarinformation för att hämta en användarentitet efter nyckel eller användarnamn i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, hämta, användare, användarinformation
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198547"
---
# <a name="get-user-information-api"></a>Hämta API för användarinformation

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
Hämta en användarentitet efter nyckel (användarnamn).

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   User.Read.All | "Läs alla användarprofiler"

## <a name="http-request"></a>HTTP-begäran
```
GET /api/users/{id}/
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och användaren finns – 200 OK med [entitet](user.md) i brödtexten. Om användaren inte finns – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

**Svar**

Här är ett exempel på svaret.


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
