---
title: Uppdatera incident-API
description: Läs om hur du uppdaterar incidenter med Microsoft 365 Defender API
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571787"
---
# <a name="update-incident-api"></a>Uppdatera incident-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="api-description"></a>API-beskrivning

Uppdaterar egenskaper för befintlig incident. Uppdatable egenskaper är: ```status``` , , , , och ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kvoter, resursallokering och andra begränsningar

1. Du kan ringa upp till 50 samtal per minut eller 1500 samtal per timme innan du når begränsningströskeln.
2. Du kan bara ange `determination` egenskapen om `classification` den är inställd på TruePositive.

Om din begäran är strypt returneras en `429` svarskod. Svarstexten anger när du kan börja ringa nya samtal.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa det här API:et. Mer information om hur du väljer behörigheter finns i Komma [åt Microsoft 365 Defender API:er](api-access.md).

Typ av behörighet | Behörighet | Namn på behörighetsvisning
-|-|-
Program | Incident.ReadWrite.All | Läsa och skriva alla incidenter
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite (på plats) | Läsa och skriva incidenter

> [!NOTE]
> När du skaffar en token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera incidenten i portalen.

## <a name="http-request"></a>HTTP-begäran

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Begär rubriker

Namn | Typ | Beskrivning
-|-|-
tillstånd | Sträng | Bärare {token}. **Obligatoriskt**.
Innehållstyp | Sträng | ansökan/json. **Obligatoriskt**.

## <a name="request-body"></a>Begär brödtext

Ange värdena för de fält som ska uppdateras i förfrågningstexten. Befintliga egenskaper som inte ingår i begärandetexten behåller sina värden, såvida de inte måste beräknas om på grund av ändringar i relaterade värden. För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.

Egenskap | Typ | Beskrivning
-|-|-
status | Uppräkning | Anger incidentens aktuella status. Möjliga värden är: ```Active``` ```Resolved``` , och ```Redirected``` .
tilldeladTill | sträng | Ägaren till incidenten.
klassificering | Uppräkning | Specifikation av incidenten. Möjliga värden är: ```Unknown``` , ```FalsePositive``` ```TruePositive``` .
beslutsamhet | Uppräkning | Anger bestämningen av incidenten. Möjliga värden är: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
Taggar | stränglista | Lista över incidenttaggar.
kommentar | sträng | Kommentar som ska läggas till i incidenten.

## <a name="response"></a>svar

Om den här metoden lyckas returneras `200 OK` . Svarstexten innehåller incidententiteten med uppdaterade egenskaper. Om en incident med det angivna ID:t inte hittades returneras metoden `404 Not Found` .

## <a name="example"></a>Exempel

**begäran**

Här är ett exempel på begäran.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**svar**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Relaterade artiklar

- [Komma åt Microsoft 365 Defender API:erna](api-access.md)
- [Lär dig mer om API-gränser och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [API:er för tillbud](api-incident.md)
- [Lista incidenter](api-list-incidents.md)
- [Översikt över incidenter](incidents-overview.md)
