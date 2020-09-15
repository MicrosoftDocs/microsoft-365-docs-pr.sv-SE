---
title: 'API: er för skydd mot Microsoft Threat'
description: 'API: er för skydd mot Microsoft Threat'
keywords: 'MTP, API: er'
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650564"
---
# <a name="supported-microsoft-threat-protection-apis"></a>API: er för skydd mot Microsoft Threat 
**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


### <a name="end-point-uris"></a>Slut punkts-URI:

- Tjänste leverantörens URI är: https://api.security.microsoft.com <br>

>[!NOTE]
>För bättre prestanda kan du använda Server närmare din Geo-plats:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - Resursen för att hämta token ska vara: https://api.security.microsoft.com

 - Alla API: er under ```/api``` Path är OData API. namn@example.com. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Lista över tillgängliga API: er

Ämnes | Beskrivning
:---|:---
[Avancerat jakt-API](api-advanced-hunting.md) | Kör avancerade frågor från API.
[API för incidenter](api-incident.md) | Kör incident närliggande API-samtal, till exempel: list incidenter, uppdaterings tillbud och mer.
