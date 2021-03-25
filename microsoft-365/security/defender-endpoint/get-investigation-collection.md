---
title: API för listundersökningar
description: Använd detta API för att skapa samtal relaterade till samlingen Undersökningar
keywords: apis, graph api, api som stöds, samlingar för undersökningar
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
ms.technology: mde
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167121"
---
# <a name="list-investigations-api"></a>API för listundersökningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hämtar en samling av [undersökningar](investigation.md).
<br>Stöder [OData V4-frågor.](https://www.odata.org/documentation/)
<br>OData-frågan ```$filter``` stöds för: ```startTime``` ```state``` , ```machineId``` och ```triggeringAlertId``` egenskaper.
<br>Se exempel på [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Begränsningar
1. Maximal sidstorlek är 10 000.
2. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme. 


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Alert.Read.All |    "Läs alla aviseringar"
Program |   Alert.ReadWrite.All |   "Läs och skriv alla aviseringar"
Delegerat (arbets- eller skolkonto) | Avisering.Läsa | Läsaviseringar
Delegerat (arbets- eller skolkonto) | Alert.ReadWrite | "Aviseringar om läsning och skrivning"

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)

## <a name="http-request"></a>HTTP-begäran
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200, Ok-svarskod med en samling enheter [för undersökningar.](investigation.md)


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på en begäran om att få alla undersökningar: 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

**Svar**

Här är ett exempel på svaret:

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
