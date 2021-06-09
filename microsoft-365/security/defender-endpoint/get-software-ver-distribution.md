---
title: Lista distribution av programvaruversion
description: Hämtar en lista över organisationens programvaruversionsdistribution
keywords: apis, graph api, API som stöds, skaffa, distribution av programvaruversion, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845036"
---
# <a name="list-software-version-distribution"></a>Lista distribution av programvaruversion 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hämtar en lista över organisationens distribution av programvaruversion. 

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program | Software.Read.All | "Läs information om hot och sårbarhetshanteringsprogramvara"
Delegerat (arbets- eller skolkonto) | Software.Read | "Läs information om hot och sårbarhetshanteringsprogramvara"

## <a name="http-request"></a>HTTP-begäran
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Begäran om rubriker

| Namn        | Typ | Beskrivning
|:--------------|:-------|:--------------|
| Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om den lyckas returnerar den här metoden 200 OK med en lista över distributionsdata för programvara i brödtexten. 


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Svar**

Här är ett exempel på svaret.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Relaterade ämnen
- [Riskbaserade hot & sårbarhetshantering](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Hot & inventering av sårbarhetsprogramvara](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
