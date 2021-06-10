---
title: Hämta CVE-KB map API
description: Lär dig hur du använder API:t Hämta CVE-KB-karta för att hämta en karta över CVE:er till KB- och CVE-information i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166893"
---
# <a name="get-cve-kb-map-api"></a>Hämta CVE-KB map API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hämtar en karta över CVE-informationen till KB- och CVE-informationen.

## <a name="permissions"></a>Behörigheter
Användaren behöver läsbehörighet.

## <a name="http-request"></a>HTTP-begäran
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>Begäran om rubriker

Sidhuvud | Värde 
:---|:---
Auktorisering | Bearer {token}. **Obligatoriskt.**
Innehållstyp | application/json

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och karta finns - 200 OK.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**Svar**

Här är ett exempel på svaret.

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
