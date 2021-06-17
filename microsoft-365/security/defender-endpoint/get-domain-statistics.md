---
title: Hämta API för domänstatistik
description: Lär dig hur du använder API:t för att hämta domänstatistik för att hämta statistik för den givna domänen i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, domän, domänrelaterade enheter
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998782"
---
# <a name="get-domain-statistics-api"></a>Hämta API för domänstatistik

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hämtar statistiken för den givna domänen.


## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   URL. Read.All |  "Läs URL:er"
Delegerat (arbets- eller skolkonto) | URL. Read.All | "Läs URL:er"

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)

## <a name="http-request"></a>HTTP-begäran
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>Frågerubriker

Rubrik | Värde 
:---|:---
Auktorisering | Bearer {token}. **Obligatoriskt.**

## <a name="request-uri-parameters"></a>Begär URI-parametrar

Namn | Typ | Beskrivning
:---|:---|:---
lookBackHours | Int32 | Definierar hur många timmar vi söker tillbaka för att få fram statistiken. Standard är 30 dagar. **Valfritt.**

## <a name="request-body"></a>Frågebrödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och domän finns - 200 OK, med statistikobjekt i svarstexten. Om domänen inte finns – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**Svar**

Här är ett exempel på svaret.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
