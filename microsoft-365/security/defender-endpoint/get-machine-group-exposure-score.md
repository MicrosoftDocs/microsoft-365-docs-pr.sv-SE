---
title: Lista över exponeringsresultat per enhetsgrupp
description: Hämtar en lista över exponeringsresultat per enhetsgrupp.
keywords: apis, graph api, api som stöds, skaffa, exponeringsresultat, enhetsgrupp, exponeringsresultat för enhetsgrupp
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fe4c2d4a4f18a1057472007f21936b4111673849
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166784"
---
# <a name="list-exposure-score-by-device-group"></a>Lista över exponeringsresultat per enhetsgrupp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hämtar en samling aviseringar som är relaterade till en viss domänadress.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program | Score.Read.All | "Read Threat and Vulnerability Management Score"
Delegerat (arbets- eller skolkonto) | Score.Read | "Read Threat and Vulnerability Management Score"

## <a name="http-request"></a>HTTP-begäran

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a>Begäran om rubriker

| Namn        | Type (Typ) | Beskrivning
|:--------------|:-------|:--------------|
| Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext

Tom

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200 OK, med en lista över exponeringsresultat per enhetsgruppsdata i svarets brödtext.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a>Svar

Här är ett exempel på svaret.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Relaterade ämnen

- [Riskbaserade hot & sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Exponeringsresultat & för hot](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
