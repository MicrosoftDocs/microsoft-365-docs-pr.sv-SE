---
title: Hämta IP-statistik-API
description: Få de senaste statistikerna för din IP med hjälp av Microsoft Defender för Endpoint.
keywords: apis, graph api, api som stöds, skaffa, ip, statistik, dokumentation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998734"
---
# <a name="get-ip-statistics-api"></a>Hämta IP-statistik-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning
Hämtar statistik för den givna IP-adressen.

## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Ip.Read.All |   "Läs IP-adressprofiler"
Delegerat (arbets- eller skolkonto) | Ip.Read.All |  "Läs IP-adressprofiler"

>[!NOTE]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)

## <a name="http-request"></a>HTTP-begäran

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-uri-parameters"></a>Begär URI-parametrar

Namn | Typ | Beskrivning
:---|:---|:---
lookBackHours | Int32 | Definierar hur många timmar vi söker tillbaka för att få fram statistiken. Standard är 30 dagar. **Valfritt.**

## <a name="request-body"></a>Frågebrödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och ip finns - 200 OK med statistiska data i brödtexten. IP finns inte – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**Svar**

Här är ett exempel på svaret.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| Namn | Beskrivning |
| :--- | :---------- |
| Organisationens organisationers | det distinkta antalet enheter som öppnade nätverksanslutningen till denna IP. |
| Org visas först | den första anslutningen för denna IP i organisationen. |
| Org senast sedd  | den sista anslutningen för denna IP i organisationen. |

> [!NOTE]
> Den här statistiken baseras på data från de senaste 30 dagarna. 
