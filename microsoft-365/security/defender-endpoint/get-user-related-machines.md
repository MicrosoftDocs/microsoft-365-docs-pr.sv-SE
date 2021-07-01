---
title: Hämta API för användarrelaterade datorer
description: Läs om hur du använder API:t hämta användarrelaterade maskiner för att hämta en samling enheter som är relaterade till ett användar-ID i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, användare, användarrelaterade aviseringar
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229461"
---
# <a name="get-user-related-machines-api"></a>Hämta API för användarrelaterade datorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning
Hämtar en samling enheter som är relaterade till ett visst användar-ID.

## <a name="limitations"></a>Begränsningar

Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |Behörighet|Visningsnamn för behörighet
:---|:---|:---
Program |Machine.Read.All|"Läs alla maskinprofiler"
Program |Machine.ReadWrite.All |"Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.Read | "Läs maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

> [!NOTE]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
> - Användaren måste ha minst följande rollbehörighet: "Visa data". Mer information finns i [Skapa och hantera roller](user-roles.md))
> - Svaret omfattar endast enheter som användaren kan komma åt, baserat på enhetens gruppinställningar. Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).

## <a name="http-request"></a>HTTP-begäran

```http
GET /api/users/{id}/machines
```

**ID:t är inte det fullständiga UPN, utan bara användarnamnet. (Till exempel för att hämta datorer för user1@contoso.com /api/users/user1/machines)**

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**

## <a name="request-body"></a>Frågebrödtext

Tom

## <a name="response"></a>Svar

Om det lyckas och användaren finns - 200 OK med en lista [över maskinenheter](machine.md) i brödtexten. Om användaren inte finns – 404 Hittades inte.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
