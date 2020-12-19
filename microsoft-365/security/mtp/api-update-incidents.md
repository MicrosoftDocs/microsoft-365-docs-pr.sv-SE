---
title: Uppdatera incident API
description: Lär dig hur du uppdaterar incidenter med hjälp av Microsoft 365 Defender API
keywords: uppdatering, API, incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719410"
---
# <a name="update-incidents-api"></a>Uppdatera incident API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

## <a name="api-description"></a>API-Beskrivning

Uppdaterar egenskaper för befintlig incident. Uppdaterings bara egenskaper är: ```status``` , ```determination``` ,, ```classification``` ```assignedTo``` och ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kvoter, resursallokering och andra villkor

1. Du kan ringa upp till 50 samtal per minut eller 1500 samtal per timme innan du klickar på tröskelvärdet för begränsning av bandbredd.
2. Du kan endast ställa in `determination` egenskapen om `classification` är inställd på TruePositive.

Om din begäran är begränsad returneras en `429` svarskod. I svars texten visas tiden då du kan börja ringa nya samtal.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att kunna ringa detta API. Mer information om hur du väljer behörigheter finns i avsnittet [om Microsoft 365 Defender API: er](api-access.md).

Behörighets typ | Tillåtelse | Visnings namn för behörighet
-|-|-
Program | Incident. ReadWrite. alla | Läsa och skriva alla händelser
Delegerat (arbets-eller skol konto) | Incident. ReadWrite | Läs-och skriv händelser

> [!NOTE]
> När du erhåller ett token med användarautentiseringsuppgifter måste användaren ha behörighet att uppdatera händelsen i portalen.

## <a name="http-request"></a>HTTP-begäran

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Begärandehuvuden

Namn | Type (Typ) | Beskrivning
-|-|-
Bemyndigande | Sträng | Bearer {token}. **Obligatoriskt**.
Innehålls typ | Sträng | Application/JSON. **Obligatoriskt**.

## <a name="request-body"></a>Brödtext

I begärans brödtext anger du värden för de fält som ska uppdateras. Befintliga egenskaper som inte är inkluderade i kravet på brödtext bibehåller sina värden, såvida de inte måste beräknas på nytt på grund av ändringar i relaterade värden. För bästa prestanda bör du utelämna befintliga värden som inte har ändrats.

Egenskap | Type (Typ) | Beskrivning
-|-|-
status | Enum | Anger aviseringens aktuella status. Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .
Tilldelat | strängvärdet | Ägaren till incidenten.
nomenklatur | Enum | Specifikation av aviseringen. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
bedömning | Enum | Anger hur aviseringen ska visas. Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
taggen | sträng lista | Lista över incident koder.

## <a name="response"></a>Interimssvar

Om det lyckas returneras den här metoden `200 OK` . Svars texten innehåller incident-enheten med uppdaterade egenskaper. Om en incident med angivet ID inte hittas returneras metoden `404 Not Found` .

## <a name="example"></a>Exempel

**Ställning**

Här är ett exempel på begäran.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Interimssvar**

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

- [Gå till API för Microsoft 365 Defender](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [API:er för tillbud](api-incident.md)
- [Lista incidenter](api-list-incidents.md)
- [Incident översikt](incidents-overview.md)
