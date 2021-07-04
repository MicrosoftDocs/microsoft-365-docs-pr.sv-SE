---
title: Skapa avisering från händelse-API
description: Lär dig hur du använder API:t för att skapa en ny avisering ovanpå händelsen i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, avisering, information, id
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
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289469"
---
# <a name="create-alert-api"></a>Skapa aviserings-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning

Skapar ny [avisering](alerts.md) ovanpå **händelse**.

- **Microsoft Defender för Endpoint-händelse** krävs för att aviseringen ska kunna skapas.
- Du måste ange 3 parametrar från händelsen i begäran: Händelsetid, **Maskin-ID** och  **Rapport-ID.** Se exemplet nedan.
- Du kan använda en händelse i Advanced Hunting API eller Portal.
- Om det finns en öppen avisering på samma enhet med samma rubrik, slås den nya skapade aviseringen ihop med den.
- En automatisk undersökning startar automatiskt för aviseringar som skapas via API:t.

## <a name="limitations"></a>Begränsningar

1. Prisbegränsningar för detta API är 15 samtal per minut.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
:---|:---|:---
Program | Alerts.ReadWrite.All | "Läs och skriv alla aviseringar"
Delegerat (arbets- eller skolkonto) | Alert.ReadWrite | "Aviseringar om läsning och skrivning"

> [!NOTE]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
> - Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)
> - Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)

## <a name="http-request"></a>HTTP-begäran

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Content-Type | Sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Frågebrödtext

Ange följande värden i brödtexten för begäran (alla är obligatoriska):

Egenskap | Typ | Beskrivning
:---|:---|:---
eventTime | DateTime(UTC) | Den exakta tiden för händelsen som sträng, från avancerad sökning. t.ex. ```2018-08-03T16:45:21.7115183Z``` **Obligatoriskt**.
reportId | Sträng | ReportId för händelsen, från avancerad sökning. **Obligatoriskt.**
machineId | Sträng | ID för enheten där händelsen identifierades. **Obligatoriskt.**
allvarlighetsgrad | Sträng | Aviseringens allvarlighetsgrad. Egenskapsvärdena är: "Låg", "Medel" och "Hög". **Obligatoriskt.**
rubrik | Sträng | Rubrik för aviseringen. **Obligatoriskt.**
description | Sträng | Beskrivning av aviseringen. **Obligatoriskt.**
recommendedAction| Sträng | En åtgärd som rekommenderas att vidtas av säkerhetsofficer när du analyserar aviseringen. **Obligatoriskt.**
kategori| Sträng | Kategorin för aviseringen. Egenskapsvärdena är: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "Malware", "Malware", "Per persist", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200 OK och ett [nytt aviseringsobjekt](alerts.md) i svarstexten. Om en händelse med de angivna egenskaperna _(reportId,_ _eventTime_ och _machineId)_ inte hittades – 404 Hittades inte.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
