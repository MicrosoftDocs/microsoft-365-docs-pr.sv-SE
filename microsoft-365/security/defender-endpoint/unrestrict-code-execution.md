---
title: Ta bort API för appbegränsning
description: Använd detta API för att skapa anrop som är relaterade till att ta bort en begränsning från program från att köra.
keywords: apis, graph api, API som stöds, ta bort enheten från isolation
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
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770883"
---
# <a name="remove-app-restriction-api"></a>Ta bort API för appbegränsning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Aktivera körning av alla program på enheten.


## <a name="limitations"></a>Begränsningar
1. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.RestrictExecution | Begränsa kodkörning
Delegerat (arbets- eller skolkonto) | Machine.RestrictExecution | Begränsa kodkörning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)
>- Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)

## <a name="http-request"></a>HTTP-begäran
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a>Begäran om rubriker
Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext
Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Typ    | Beskrivning
:---|:---|:---
Kommentar |   Sträng | Kommentar som ska associeras med åtgärden. **Obligatoriskt.**

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


Information om hur du begränsar kodkörning på en enhet finns [i Begränsa programkörning.](restrict-code-execution.md)
