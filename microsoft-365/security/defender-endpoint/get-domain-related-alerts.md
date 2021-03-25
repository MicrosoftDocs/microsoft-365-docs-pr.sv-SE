---
title: Skaffa API för domänrelaterade aviseringar
description: Lär dig hur du använder API:t för att hämta domänrelaterade aviseringar för att hämta aviseringar relaterade till en viss domänadress i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, domän, relaterade, aviseringar
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166869"
---
# <a name="get-domain-related-alerts-api"></a>Skaffa API för domänrelaterade aviseringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hämtar en samling aviseringar [som är](alerts.md) relaterade till en viss domänadress.


## <a name="limitations"></a>Begränsningar
1. Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.
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
>- Svaret inkluderar endast aviseringar, som associeras med enheter, som användaren har [](machine-groups.md) åtkomst till, baserat på enhetsgruppsinställningar (mer information finns i Skapa och hantera enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>Begäran om rubriker

| Sidhuvud        | Value  |
|:--------------|:-------|
| Auktorisering | Sträng |

## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och domänen finns – 200 OK med lista över [aviseringsenheter.](alerts.md) Om domänen inte finns – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
