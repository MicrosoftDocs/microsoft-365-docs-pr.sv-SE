---
title: Få enhet säker poäng
description: Hämtar organisationens säkerhetsresultat.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166882"
---
# <a name="get-device-secure-score"></a>Få enhet säker poäng

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Hämtar Microsoft [Secure Score för enheter.](tvm-microsoft-secure-score-devices.md) Ett högre Microsoft Secure Score för enheter innebär att dina slutpunkter är mer flexibel mot attacker mot hot om cyberhot. 

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Score.Read.Alll |   "Read Threat and Vulnerability Management Score"
Delegerat (arbets- eller skolkonto) | Score.Read | "Read Threat and Vulnerability Management Score"

## <a name="http-request"></a>HTTP-begäran

```
GET /api/configurationScore
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext

Tom

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200 OK, med enhetens säkra poängdata i svarstexten.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a>Svar

Här är ett exempel på svaret.

>[!NOTE]
>Svarslistan som visas här kan trunkeras för att vara kort. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>Se även

- [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)
