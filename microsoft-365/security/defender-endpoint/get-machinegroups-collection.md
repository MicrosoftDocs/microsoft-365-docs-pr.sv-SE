---
title: Hämta API för RBAC-maskingrupper
description: Lär dig hur du använder API:t för att hämta KB-samlings-API:t för att hämta en samling RBAC-enhetsgrupper i Microsoft Defender Advanced Threat Protection.
keywords: apis, graph api, API som stöds, get, RBAC, grupp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167025"
---
# <a name="get-kb-collection-api"></a>Hämta API för KB-samling

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Hämtar en samling av RBAC-enhetsgrupper.

## <a name="permissions"></a>Behörigheter
Användaren behöver läsbehörighet.

## <a name="http-request"></a>HTTP-begäran
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Begäran om rubriker

Sidhuvud | Value 
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

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Svar**

Här är ett exempel på svaret.
Fält-ID innehåller enhetens **grupp-ID** och är lika med **fält rbacGroupId** i enhetsinformationen. Fält **som inte har** grupperats gäller endast för en grupp för alla enheter som inte har tilldelats någon grupp. Den här gruppen har som vanligt namnet "Ej tilldelad grupp".

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
