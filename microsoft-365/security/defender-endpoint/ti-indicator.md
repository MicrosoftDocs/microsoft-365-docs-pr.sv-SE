---
title: Indikatorresurstyp
description: Ange entitetsinformation och definiera förfallotiden för indikatorn med Hjälp av Microsoft Defender för Slutpunkt.
keywords: apis, apis som stöds, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771387"
---
# <a name="indicator-resource-type"></a>Indikatorresurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Se motsvarande [indikatorsida](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) i portalen. 

Metod|Returtyp |Beskrivning
:---|:---|:---
[Lista indikatorer](get-ti-indicators-collection.md) | [Indikator](ti-indicator.md) Samling | Enheter [med listindikator.](ti-indicator.md)
[Skicka indikator](post-ti-indicator.md) | [Indikator](ti-indicator.md) | Skicka eller uppdatera [indikator entitet.](ti-indicator.md)
[Importindikatorer](import-ti-indicators.md) | [Indikator](ti-indicator.md) Samling | Skicka eller uppdatera [indikatorer.](ti-indicator.md)
[Ta bort indikator](delete-ti-indicator-by-id.md) | Inget innehåll | Tar bort [indikator entitet.](ti-indicator.md)


## <a name="properties"></a>Egenskaper
Egenskap |  Typ    |   Beskrivning
:---|:---|:---
id | Sträng | Identiteten för [indikatorenheten.](ti-indicator.md)
indicatorValue | Sträng | Värdet på [indikatorn](ti-indicator.md).
indicatorType | Uppräkning | Typ av indikator. Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url".
program | Sträng | Programmet som är kopplat till indikatorn. 
åtgärd | Uppräkning | Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen. Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet".
sourceType | Uppräkning | "Användare" om indikatorn skapades av en användare (t.ex. från portalen), "AadApp" om den skickades med automatiserad ansökan via API:t.
källa | sträng | Namnet på den användare/det program som skickade indikatorn.
createdBy | Sträng | Unik identitet för användaren/programmet som skickade indikatorn.
lastUpdatedBy | Sträng | Identiteten för den användare/det program som senast uppdaterade indikatorn.
creationTimeDateTimeUtc | DateTimeOffset | Datum och tid då indikatorn skapades.
expirationTime | DateTimeOffset | Indikatorns utgångstid.
lastUpdateTime | DateTimeOffset | Den senaste gången indikatorn uppdaterades.
allvarlighetsgrad | Uppräkning | Indikatorns allvarlighetsgrad. Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög".
rubrik | Sträng | Indikatorrubrik.
beskrivning | Sträng | Beskrivning av indikatorn.
recommendedActions | Sträng | Rekommenderade åtgärder för indikatorn.
rbacGroupNames | Lista med strängar | Gruppnamn på RBAC-enheter där indikatorn exponeras och är aktiv. Tom lista om den exponeras för alla enheter.


## <a name="json-representation"></a>Json-representation

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
