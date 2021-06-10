---
title: Hämta API för KB-samling
description: Hämta en samling kunskapsbaser (kB) och KB-information med Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, kb
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
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167181"
---
# <a name="get-kb-collection-api"></a>Hämta API för KB-samling

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hämtar en samling kb- och KB-information.

## <a name="permissions"></a>Behörigheter
Användaren behöver läsbehörighet.

## <a name="http-request"></a>HTTP-begäran
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>Begäran om rubriker

Sidhuvud | Värde 
:---|:---
Auktorisering | Bearer {token}. **Obligatoriskt.**
Innehållstyp | application/json

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas – 200 OK.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**Svar**

Här är ett exempel på svaret.

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
