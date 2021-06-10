---
title: API för import av indikatorer
description: Lär dig hur du använder importbatchen av indikator-API i Microsoft Defender för Slutpunkt.
keywords: apis, apis som stöds, skicka, ti, indikator, uppdatera
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198251"
---
# <a name="import-indicators-api"></a>API för import av indikatorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Batchen Skicka eller Uppdateringar med [indikatorenheter.](ti-indicator.md)
<br>CIDR-notation för IP-adresser stöds inte.

## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 30 samtal per minut.
2. Det finns en gräns på 15 000 aktiva [indikatorer](ti-indicator.md) per klientorganisation. 
3. Den maximala batchstorleken för ett API-anrop är 500.

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Ti.ReadWrite |  Indikatorer för läsning och skrivning
Program |   Ti.ReadWrite.All |  "Läsa och skriva alla indikatorer"
Delegerat (arbets- eller skolkonto) |    Ti.ReadWrite |  Indikatorer för läsning och skrivning


## <a name="http-request"></a>HTTP-begäran
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext
Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Typ    | Beskrivning
:---|:---|:---
Indikatorer | Indikator<[lista](ti-indicator.md)> | Lista över [indikatorer](ti-indicator.md). **Obligatoriskt**


## <a name="response"></a>Svar
- Om det lyckas returnerar den här metoden 200 – OK-svarskod med en lista med importresultat per indikator, se exemplet nedan.
- Om det inte lyckas: den här metoden returnerar 400 – Bad Request. Felaktig begäran anger vanligtvis felaktigt brödtext.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

**Svar**

Här är ett exempel på svaret.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Relaterat ämne
- [Hantera indikatorer](manage-indicators.md)
