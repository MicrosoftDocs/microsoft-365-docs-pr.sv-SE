---
title: Hämta programvara genom Id
description: Hämtar en lista över exponeringsresultat per enhetsgrupp.
keywords: apis, graph api, api som stöds, skaffa, programvara, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198595"
---
# <a name="get-software-by-id"></a>Hämta programvara genom Id

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hämtar programvaruinformation efter ID.

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program | Software.Read.All | "Läs information om hot och sårbarhetshanteringsprogramvara"
Delegerat (arbets- eller skolkonto) | Software.Read | "Läs information om hot och sårbarhetshanteringsprogramvara"

## <a name="http-request"></a>HTTP-begäran
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a>Begäran om rubriker

| Namn        | Skriv | Beskrivning
|:--------------|:-------|:--------------|
| Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200 OK med angivna programvarudata i brödtexten. 


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

**Svar**

Här är ett exempel på svaret.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>Relaterade ämnen
- [Riskbaserade hot & sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Hot & inventering av sårbarhetsprogramvara](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
