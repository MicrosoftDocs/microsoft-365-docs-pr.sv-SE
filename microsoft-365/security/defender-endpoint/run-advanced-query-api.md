---
title: Advanced jakt-API
ms.reviewer: ''
description: Lär dig att använda API:t för avancerad sökning till att köra avancerade frågor på Microsoft Defender för Slutpunkt. Läs mer om begränsningar och se ett exempel.
keywords: apis, apis som stöds, avancerad sökning, fråga
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
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604387"
---
# <a name="advanced-hunting-api"></a>Api för avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Begränsningar

1. Du kan endast köra en fråga på data från de senaste 30 dagarna.

2. Resultatet kommer att innehålla högst 100 000 rader.

3. Antalet körningar är begränsat per klientorganisation:
   - API-samtal: Upp till 45 samtal per minut, upp till 1 500 samtal per timme.
   - Körningstid: 10 minuters körningstid varje timme och 3 timmars körningstid per dag.

4. Den maximala körningstiden för en enskild begäran är 10 minuter.

5. 429-svar motsvarar att nå en kvotgräns, antingen genom antal begäranden eller av cpu:n. Läs svarstext för att förstå vilken gräns som har nåtts. 

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   AdvancedQuery.Read.All |    Kör avancerade frågor
Delegerat (arbets- eller skolkonto) | AdvancedQuery.Read | Kör avancerade frågor

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha AD-rollen "Visa data"
>- Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Begäran om rubriker

Sidhuvud | Värde 
:---|:---
Auktorisering | Bearer {token}. **Obligatoriskt.**
Innehållstyp    | application/json

## <a name="request-body"></a>Begärans brödtext

Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Skriv    | Beskrivning
:---|:---|:---
Fråga | Text |  Frågan som ska köras. **Obligatoriskt.**

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200 OK och _objektet QueryResponse_ i svarstexten.


## <a name="example"></a>Exempel

##### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a>Svar

Här är ett exempel på svaret.

>[!NOTE]
>Det svarsobjekt som visas här kan trunkeras för korthet. Alla egenskaper returneras från ett faktiskt samtal.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>Relaterade ämnen

- [Introduktion till MICROSOFT Defender för slutpunkts-API:er](apis-intro.md)
- [Avancerad sökning från portalen](advanced-hunting-query-language.md)
- [Avancerad jakt med PowerShell](run-advanced-query-sample-powershell.md)
