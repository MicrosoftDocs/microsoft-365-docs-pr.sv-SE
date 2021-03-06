---
title: API för insamling av undersökningspaket
description: Använd detta API för att skapa anrop som är relaterade till insamling av ett undersökningspaket från en enhet.
keywords: apis, graph api, api som stöds, paket för insamling av undersökning
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
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289901"
---
# <a name="collect-investigation-package-api"></a>API för insamling av undersökningspaket

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning

Samla in undersökningspaket från en enhet.

## <a name="limitations"></a>Begränsningar

1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
:---|:---|:---
Program | Machine.CollectForensics | "Samla in en forensiska"
Delegerat (arbets- eller skolkonto) | Machine.CollectForensics | "Samla in en forensiska"

> [!NOTE]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
> - Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)
> - Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Content-Type | sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Frågebrödtext

Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Typ | Beskrivning
:---|:---|:---
Kommentar | Sträng | Kommentar som ska associeras med åtgärden. **Obligatoriskt.**

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.

## <a name="example"></a>Exempel

### <a name="request"></a>Begäran

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
