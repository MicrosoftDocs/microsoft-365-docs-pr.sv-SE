---
title: API för listdatorer
description: Lär dig hur du använder List machines API till att hämta en samling datorer som har kommunicerat med Microsoft Defender för Endpoint Cloud.
keywords: apis, graph api, API som stöds, skaffa, enheter
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
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d52e1b69311c26144684b90545e17934d1223332
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287861"
---
# <a name="list-machines-api"></a>API för listdatorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning
Hämtar en samling datorer som [har](machine.md) kommunicerat med Microsoft Defender för Endpoint-molnet.
<br>Stöder [OData V4-frågor.](https://www.odata.org/documentation/)
<br>OData-frågan `$filter` stöds på: `computerDnsName` , `lastSeen` , , `healthStatus` och `osPlatform` `riskScore` `rbacGroupId` .
<br>Se exempel på [OData-frågor med Defender för Slutpunkt](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Begränsningar
1. Du kan se till att enheter visas senast enligt din konfigurerade lagringstid.
2. Maximal sidstorlek är 10 000.
3. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme. 


## <a name="permissions"></a>Behörigheter

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.Read.All |  "Läs alla maskinprofiler"
Program |   Machine.ReadWrite.All | "Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.Read | "Läs maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)
>- Svaret omfattar endast enheter, som användaren har åtkomst till, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Frågebrödtext
Tom

## <a name="response"></a>Svar
Om lyckat, och datorer finns - 200 OK med en lista [över maskinenheter](machine.md) i brödtexten. Om det inte finns några senaste datorer - 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Svar**

Här är ett exempel på svaret.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Relaterade ämnen
- [OData-frågor med Microsoft Defender för Slutpunkt](exposed-apis-odata-samples.md)
