---
title: Få saknade KBs efter enhets-ID
description: Hämtar säkerhetsuppdateringar efter enhets-ID
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, enhets-ID, & sårbarhetshantering api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4364e6a38d4597a95d4d9a1f05dcce6fce5797ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500693"
---
# <a name="get-missing-kbs-by-device-id"></a>Få saknade KBs efter enhets-ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hämtar saknade KBs (säkerhetsuppdateringar) efter enhets-ID

## <a name="http-request"></a>HTTP-begäran

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a>Sidhuvud för begäran

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext

Tom

## <a name="response"></a>Svar

Om den lyckas returnerar den här metoden 200 OK, när den angivna enheten saknar KB-data i brödtexten.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a>Svar

Här är ett exempel på svaret.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a>Relaterade ämnen

- [Riskbaserade hot & sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Hot & inventering av sårbarhetsprogramvara](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
