---
title: Indikator-API för Skicka eller uppdatera
description: Lär dig hur du använder indikator-API:t för skicka eller uppdatera för att skicka eller uppdatera en ny indikator i Microsoft Defender för slutpunkt.
keywords: apis, graph api, apis som stöds, skicka, ti, indikator, uppdatera
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187363"
---
# <a name="submit-or-update-indicator-api"></a>Indikator-API för Skicka eller uppdatera

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning
Skickar eller uppdaterar ny [indikator entitet.](ti-indicator.md)
<br>CIDR-notation för IP-adresser stöds inte.

## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.
2. Det finns en gräns på 15 000 aktiva indikatorer per klientorganisation. 


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Ti.ReadWrite |  Indikatorer för läsning och skrivning
Program |   Ti.ReadWrite.All |  "Läsa och skriva alla indikatorer"
Delegerat (arbets- eller skolkonto) |    Ti.ReadWrite |  Indikatorer för läsning och skrivning


## <a name="http-request"></a>HTTP-begäran
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext
Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Skriv    | Beskrivning
:---|:---|:---
indicatorValue | Sträng | Identiteten för [indikatorenheten.](ti-indicator.md) **Obligatoriskt**
indicatorType | Uppräkning | Typ av indikator. Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url". **Obligatoriskt**
åtgärd | Uppräkning | Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen. Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet". **Obligatoriskt**
program | Sträng | Programmet som är kopplat till indikatorn. **Valfritt**
rubrik | Sträng | Indikatoraviseringens rubrik. **Obligatoriskt**
beskrivning | Sträng | Beskrivning av indikatorn. **Obligatoriskt**
expirationTime | DateTimeOffset | Indikatorns utgångstid. **Valfritt**
allvarlighetsgrad | Uppräkning | Indikatorns allvarlighetsgrad. Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög". **Valfritt**
recommendedActions | Sträng | Rekommenderade åtgärder för TI-indikatoraviseringar. **Valfritt**
rbacGroupNames | Sträng | Kommaavgränsade listor med namn på RBAC-grupper indikatorn skulle tillämpas på. **Valfritt**


## <a name="response"></a>Svar
- Om det lyckas returnerar den här metoden 200 – OK-svarskod och den skapade/uppdaterade [indikatorentiteten](ti-indicator.md) i svarstexten.
- Om det inte lyckas: den här metoden returnerar 400 – Bad Request. Felaktig begäran anger vanligtvis felaktigt brödtext.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Relaterat ämne
- [Hantera indikatorer](manage-indicators.md)
