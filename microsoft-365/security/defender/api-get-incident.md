---
title: Hämta incident-API
description: Läs om hur du använder API:t Hämta incidenter för att få en enda incident i Microsoft 365 Defender.
keywords: apis, graph api, API som stöds, skaffa, fil, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289613"
---
# <a name="get-incident-information-api"></a>Hämta API för incidentinformation

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning

Hämtar ett specifikt incident med dess ID

## <a name="limitations"></a>Begränsningar

1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. 

Behörighetstyp | Behörighet | Visningsnamn för behörighet
:---|:---|:---
Program | Incident.Read.All | "Läs alla incidenter"
Program | Incident.ReadWrite.All | "Läsa och skriva alla incidenter"
Delegerat (arbets- eller skolkonto) | Incident.Read | "Läs incidenter"
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite | "Läsa och skriva incidenter"

> [!NOTE]
>
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
> - Användaren måste ha minst följande rollbehörighet: 'Visa data'
> - Svaret inkluderar endast incidenter som användaren exponeras för

## <a name="http-request"></a>HTTP-begäran

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Frågebrödtext

Tom

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 200 OK och incidenten i svarstexten. Om incident med det angivna ID:t inte hittades – 404 Hittades inte.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
