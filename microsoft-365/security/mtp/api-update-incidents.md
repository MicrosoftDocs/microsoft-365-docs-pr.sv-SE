---
title: Uppdatera incident API
description: Lär dig hur du uppdaterar incidenter med hjälp av Microsoft Threat Protection API
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203646"
---
# <a name="update-incidents-api"></a>Uppdatera incident API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


## <a name="api-description"></a>API-Beskrivning
Uppdaterar egenskaper för befintlig incident.
<br>Uppdaterings bara egenskaper är: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` och ```tags``` .


## <a name="limitations"></a>Begränsningar
1. Pris begränsningar för detta API är 50 samtal per minut och 1500 samtal per timme.
2. Du kan endast ange ```determination``` om klassificeringen är inställd på TruePositive.


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att kunna ringa detta API. Om du vill veta mer, inklusive hur du väljer behörigheter, kan du läsa [gå till Microsoft Threat Protection API: er](api-access.md).

Behörighets typ |   Tillåtelse  |   Visnings namn för behörighet
:---|:---|:---
Program |   Incident. ReadWrite. alla |    "Läs och skriv alla händelser"
Delegerat (arbets-eller skol konto) | Incident. ReadWrite | "Läs-och skriv händelser"

>[!NOTE]
> När du erhåller ett token med användar uppgifter:
>- Användaren måste ha behörighet att uppdatera händelsen i portalen.


## <a name="http-request"></a>HTTP-begäran

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Begärandehuvuden

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Bemyndigande | Sträng | Bearer {token}. **Obligatoriskt**.
Innehålls typ | Sträng | Application/JSON. **Obligatoriskt**.


## <a name="request-body"></a>Brödtext
Ange värdena för de relevanta fält som ska uppdateras i begärans brödtext.
<br>Befintliga egenskaper som inte är inkluderade i kravet på brödtext bibehåller sina tidigare värden eller omräknas om till ändringar i andra egenskaps värden. 
<br>För bästa prestanda bör du inte ta med befintliga värden som inte har ändrats.

Egenskap | Type (Typ) | Beskrivning
:---|:---|:---
status | Enum | Anger aviseringens aktuella status. Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .
Tilldelat | strängvärdet | Ägaren till incidenten.
nomenklatur | Enum | Specifikation av aviseringen. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
bedömning | Enum | Anger hur aviseringen ska visas. Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
taggen | sträng lista | Lista över incident koder.



## <a name="response"></a>Interimssvar
Om det lyckas returnerar den här metoden 200 OK och incidenten i svars texten med de uppdaterade egenskaperna. Om det inte finns någon incident med det angivna ID: t hittas inte 404.


## <a name="example"></a>Exempel

**Ställning**

Här är ett exempel på begäran.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Närliggande ämne
- [API:er för tillbud](api-incident.md)
- [Lista incidenter](api-list-incidents.md)
