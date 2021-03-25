---
title: Skaffa API för domänrelaterade datorer
description: Lär dig hur du använder API för domänrelaterade datorer för att få datorer som kommunicerar till eller från en domän i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, domän, relaterade, enheter
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166881"
---
# <a name="get-domain-related-machines-api"></a>Skaffa API för domänrelaterade datorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Hämtar en samling datorer [som](machine.md) har kommunicerat till eller från en viss domänadress.


## <a name="limitations"></a>Begränsningar
1. Du kan fråga på enheter som senast uppdaterades enligt din konfigurerade lagringstid.
2. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.Read.All |  "Läs alla maskinprofiler"
Program |   Machine.ReadWrite.All | "Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.Read | "Läs maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)
>- Svaret omfattar endast enheter som användaren kan komma åt, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Tom

## <a name="response"></a>Svar
Om det lyckas och det finns en domän – 200 OK med en lista över [datorenheter.](machine.md) Om domänen inte finns – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
