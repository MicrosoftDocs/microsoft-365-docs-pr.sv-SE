---
title: API för batchuppdateringsaviseringsenheter
description: Lär dig hur du uppdaterar Microsoft Defender för slutpunktsaviseringar i en batch med hjälp av detta API. Du kan uppdatera status, determination, klassificering och tilldeladeTill-egenskaper.
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167086"
---
# <a name="batch-update-alerts"></a>Batchuppdateringsaviseringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beskrivning
Uppdaterar egenskaper för en batch med befintliga [aviseringar.](alerts.md)
<br>**Kommentarsinskick** är tillgängligt med eller utan uppdatering av egenskaper.
<br>Egenskaper som kan uppdateras är: `status` `determination` , och `classification` `assignedTo` .


## <a name="limitations"></a>Begränsningar
1. Du kan uppdatera aviseringar som är tillgängliga i API:et. Mer information finns i Listaviseringar. [](get-alerts.md)
2. Begränsningar i kursen för detta API är 10 samtal per minut och 500 samtal per timme.


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
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | Sträng | application/json. **Obligatoriskt.**


## <a name="request-body"></a>Begärans brödtext
Ange i meddelandetexten för begäran de aviseringar som ska uppdateras och värdena för de relevanta fält som du vill uppdatera för dessa aviseringar.
<br>Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden. 
<br>För bästa prestanda bör du inte inkludera befintliga värden som inte har ändrats.

Egenskap | Type (Typ) | Beskrivning
:---|:---|:---
alertids | &lt;Liststräng&gt;| En lista med DE IDENTIFIERINGS-identifieringar av aviseringar som ska uppdateras. **Obligatoriskt**
status | Sträng | Anger uppdaterad status för angivna aviseringar. Egenskapsvärdena är: "Ny", "InProgress" och "Löst".
assignedTo | Sträng | Ägare av angivna aviseringar
klassificering | Sträng | Anger specifikationen för de angivna aviseringarna. Egenskapsvärdena är: "Okänt", "FalsktPositiv", "SantPositiv". 
determination | Sträng | Anger vilka aviseringar som ska avgöras. Egenskapsvärdena är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
kommentar | Sträng | Kommentar som ska läggas till i de angivna aviseringarna.

## <a name="response"></a>Svar
Om det lyckas returnerar den här metoden 200 OK, med en tom svarstext.


## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
