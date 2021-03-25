---
title: Hämta installerad programvara
description: Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaruinventering, installerad programvara per enhet, & api för sårbarhetshantering, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 6164020ef05561563fe0434bd2edac8c7b3e689a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166814"
---
# <a name="get-installed-software"></a>Hämta installerad programvara

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |Software.Read.All |    "Läs information om hot och sårbarhetshanteringsprogramvara"
Delegerat (arbets- eller skolkonto) | Software.Read |    "Läs information om hot och sårbarhetshanteringsprogramvara"

## <a name="http-request"></a>HTTP-begäran
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200 OK med information om installerad programvara i brödtexten.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

**Svar**

Här är ett exempel på svaret.


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a>Se även

- [Riskbaserade hot & sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Hot & inventering av sårbarhetsprogramvara](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
