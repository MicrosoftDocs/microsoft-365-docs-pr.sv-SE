---
title: Api för Offboard-dator
description: Lär dig hur du använder ett API för att ta bort en enhet från Microsoft Defender för Endpoint.
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
ms.technology: mde
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934183"
---
# <a name="offboard-machine-api"></a>Api för Offboard-dator

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Offboard-enhet från Defender för Slutpunkt.


## <a name="limitations"></a>Begränsningar
 - Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> Detta API stöds i Windows 10, version 1703 och senare, eller Windows Server 2019 och senare. Detta API stöds inte på MacOS- eller Linux-enheter.

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.Offboard |  'Offboard machine'
Delegerat (arbets- eller skolkonto) |    Machine.Offboard |  'Offboard machine'

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha AD-roll som global administratör
>- Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
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
Kommentar |   Sträng |    Kommentar som ska associeras med åtgärden. **Obligatoriskt.**

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
