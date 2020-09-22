---
title: 'API: er som stöds av Microsoft Hotskydd'
description: 'API: er som stöds av Microsoft Hotskydd'
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203701"
---
# <a name="supported-microsoft-threat-protection-apis"></a>API: er som stöds av Microsoft Hotskydd 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

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
[Advanced jakt-API](api-advanced-hunting.md) | Kör avancerade frågor från API.
[API:er för tillbud](api-incident.md) | Kör incident närliggande API-samtal, till exempel: list incidenter, uppdaterings tillbud och mer.
