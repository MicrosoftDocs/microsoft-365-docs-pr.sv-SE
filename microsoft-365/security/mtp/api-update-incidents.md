---
title: API för uppdatering av incidenter
description: Lär dig hur du uppdaterar incidenter med Microsoft 365 Defender API
keywords: uppdatering, api, incident
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929076"
---
# <a name="update-incidents-api"></a>API för uppdatering av incidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="api-description"></a>API-beskrivning

Uppdateringsegenskaper för befintliga incidenter. Egenskaper som kan uppdateras är: ```status``` , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kvoter, resurstilldelning och andra villkor

1. Du kan ringa upp till 50 samtal per minut eller 1 500 samtal per timme innan du kommer upp till tröskelvärdet för begränsning.
2. Du kan bara ange `determination` egenskapen om den är inställd på `classification` TruePositive.

Om din begäran begränsas returneras en `429` svarskod. Svarstexten anger när du kan börja ringa nya samtal.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Access API:er för [Microsoft 365 Defender.](api-access.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
-|-|-
Program | Incident.ReadWrite.All | Läsa och skriva alla incidenter
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite | Läs- och skrivincidenter

> [!NOTE]
> När du skaffar en token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera incidenten i portalen.

## <a name="http-request"></a>HTTP-begäran

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Begär sidhuvuden

Namn | Type (Typ) | Beskrivning
-|-|-
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | Sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärandetext

Ange värden för fälten som ska uppdateras i begärans brödtext. Befintliga egenskaper som inte ingår i begärans brödtext behåller sina värden, såvida de inte behöver beräknas om på grund av ändringar av relaterade värden. För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.

Egenskap | Type (Typ) | Beskrivning
-|-|-
status | Uppräkning | Anger aktuell status för aviseringen. Möjliga värden är: ```Active``` ```Resolved``` och ```Redirected``` .
assignedTo | sträng | Ägaren till incidenten.
klassificering | Uppräkning | Specifikation för aviseringen. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determination | Uppräkning | Anger aviseringens avgörande. Möjliga värden är: ```NotAvailable``` , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
taggar | stränglista | Lista över incidenttaggar.

## <a name="response"></a>Svar

Om det lyckas returnerar den här `200 OK` metoden. Svarstexten innehåller incidententitet med uppdaterade egenskaper. Om en incident med det angivna ID:t inte hittas returneras `404 Not Found` metoden.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på begäran.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Svar**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Relaterade artiklar

- [Få åtkomst till API:er för Microsoft 365 Defender](api-access.md)
- [Läs mer om API-begränsningar och -licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [API:er för tillbud](api-incident.md)
- [Lista incidenter](api-list-incidents.md)
- [Översikt över incidenter](incidents-overview.md)
