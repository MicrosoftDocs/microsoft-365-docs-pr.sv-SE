---
title: Uppdatera API för dator entitet
description: Lär dig hur du uppdaterar datortaggar med hjälp av detta API. Du kan uppdatera egenskaperna för taggar och enhetsvärde.
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985772"
---
# <a name="update-machine"></a>Uppdatera dator 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Uppdaterar egenskaper för befintlig [dator.](machine.md)
<br>Egenskaper som kan uppdateras är: ```machineTags``` och ```deviceValue``` .


## <a name="limitations"></a>Begränsningar
1. Du kan uppdatera datorer som är tillgängliga i API:et. 
2. Update machine lägger bara till taggar i taggsamlingen. Om det finns taggar måste de inkluderas i taggsamlingen i brödtexten.
3. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Machine.ReadWrite.All | "Läsa och skriva maskininformation för alla datorer"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar". Mer information finns i Skapa [och hantera roller.](user-roles.md)
>- Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetens gruppinställningar. Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).

## <a name="http-request"></a>HTTP-begäran
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Frågerubriker

Namn | Typ | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Content-Type | Sträng | application/json. **Obligatoriskt.**


## <a name="request-body"></a>Frågebrödtext
Ange värden för de relevanta fält som ska uppdateras i begärans brödtext.
<br>Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden. 
<br>För bästa prestanda bör du inte inkludera befintliga värden som inte har ändrats.

Egenskap | Typ | Beskrivning
:---|:---|:---
machineTags | Strängsamling | Uppsättning [maskintaggar.](machine.md)
deviceValue | Nullbar uppräkning | Enhetens [värde.](tvm-assign-device-value.md) Möjliga värden är: "Normal", "Låg" och "Hög".

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200 OK, [och](machine.md) datorenheten i svarstexten med de uppdaterade egenskaperna. Om insamling av maskintaggar i brödtexten inte innehåller befintliga maskintaggar – 400 ogiltiga indata och ett meddelande om saknade taggar.
Om ingen dator med det angivna ID:t hittades – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
