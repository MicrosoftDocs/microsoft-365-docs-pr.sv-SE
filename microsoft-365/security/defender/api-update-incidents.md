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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d6872a7a4b1b2d2c131066076af02a65b4ef6d8a
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107610"
---
# <a name="update-incidents-api"></a>API för uppdatering av incidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="api-description"></a>API-beskrivning

Uppdaterar egenskaper för befintliga incidenter. Egenskaper som kan uppdateras är: ```status``` , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kvoter, resurstilldelning och andra villkor

1. Du kan ringa upp till 50 samtal per minut eller 1 500 samtal per timme innan du kommer till begränsningströskeln.
2. Du kan bara ange `determination` egenskapen om är Inställd på `classification` TruePositive.

Om din begäran begränsas returneras en `429` svarskod. Svarstexten anger när du kan börja ringa nya samtal.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Komma åt Microsoft 365 Defender-API:er.](api-access.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
-|-|-
Program | Incident.ReadWrite.All | Läsa och skriva alla incidenter
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite | Läs- och skrivincidenter

> [!NOTE]
> När användaren skaffar en token med användarautentiseringsuppgifter måste han eller hon ha behörighet att uppdatera incidenten i portalen.

## <a name="http-request"></a>HTTP-begäran

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
-|-|-
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | Sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext

Ange värden för fälten som ska uppdateras i brödtexten för begäran. Befintliga egenskaper som inte finns i begärans brödtext bibehåller sina värden, såvida de inte behöver beräknas om på grund av ändringar av relaterade värden. För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.

Egenskap | Skriv | Beskrivning
-|-|-
status | Uppräkning | Anger incidentens aktuella status. Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .
assignedTo | sträng | Ägaren till händelsen.
klassificering | Uppräkning | Specifikation för incidenten. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determination | Uppräkning | Anger incidentens avgörande. Möjliga värden är: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
taggar | stränglista | Lista över incidenttaggar.

## <a name="response"></a>Svar

Om det lyckas returnerar den här metoden `200 OK` . Svarstexten innehåller incidententitet med uppdaterade egenskaper. Om en incident med det angivna ID:t inte hittas returnerar metoden `404 Not Found` .

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

- [Komma åt Microsoft 365 Defender-API:er](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [API:er för tillbud](api-incident.md)
- [Lista incidenter](api-list-incidents.md)
- [Översikt över incidenter](incidents-overview.md)
