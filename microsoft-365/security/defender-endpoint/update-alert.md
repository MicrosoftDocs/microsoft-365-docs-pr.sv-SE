---
title: Uppdatera API för avisering entitet
description: Lär dig hur du uppdaterar en Microsoft Defender för slutpunktsavisering med hjälp av detta API. Du kan uppdatera status, determination, klassificering och tilldeladeTill-egenskaper.
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
ms.technology: mde
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688255"
---
# <a name="update-alert"></a>Uppdateringsavisering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Uppdaterar egenskaper för befintlig [avisering](alerts.md).
<br>**Kommentarsinskick** är tillgängligt med eller utan uppdatering av egenskaper.
<br>Egenskaper som kan uppdateras är: ```status``` ```determination``` , och ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Begränsningar
1. Du kan uppdatera aviseringar som är tillgängliga i API:et. Mer information finns i Listaviseringar. [](get-alerts.md)
2. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |   Behörighet  |   Visningsnamn för behörighet
:---|:---|:---
Program |   Alerts.ReadWrite.All |  "Läs och skriv alla aviseringar"
Delegerat (arbets- eller skolkonto) | Alert.ReadWrite | "Aviseringar om läsning och skrivning"

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>- Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)
>- Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)

## <a name="http-request"></a>HTTP-begäran
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | Sträng | application/json. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Ange värden för de relevanta fält som ska uppdateras i begärans brödtext.
<br>Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden. 
<br>För bästa prestanda bör du inte inkludera befintliga värden som inte ändras.

Egenskap | Skriv | Beskrivning
:---|:---|:---
status | Sträng | Anger aktuell status för aviseringen. Egenskapsvärdena är: "Ny", "InProgress" och "Löst".
assignedTo | Sträng | Ägaren av aviseringen
klassificering | Sträng | Anger specifikationen för aviseringen. Egenskapsvärdena är: "Okänt", "FalsktPositiv", "SantPositiv". 
determination | Sträng | Anger om aviseringen är bestämd. Egenskapsvärdena är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
kommentar | Sträng | Kommentar som ska läggas till i aviseringen.

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden [](alerts.md) 200 OK, och aviseringsentitet i svarstexten med de uppdaterade egenskaperna. Om aviseringen med det angivna ID:t inte hittades – 404 Hittades inte.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
