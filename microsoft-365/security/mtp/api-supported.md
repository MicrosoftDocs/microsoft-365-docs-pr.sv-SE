---
title: 'Microsoft 365 Defender API: er som stöds'
description: 'Microsoft 365 Defender API: er som stöds'
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719328"
---
# <a name="supported-microsoft-365-defender-apis"></a>Microsoft 365 Defender API: er som stöds 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

## <a name="list-of-available-apis"></a>Lista över tillgängliga API: er

Artiklar | Beskrivning
-|-
[Advanced jakt-API](api-advanced-hunting.md) | Kör avancerade jakt frågor.
[API:er för tillbud](api-incident.md) | Lista och uppdatera händelser samt andra praktiska uppgifter.

### <a name="endpoint-uris"></a>Slut punkts-URI

Bas-URI för båda huvud gränssnitten är: https://api.security.microsoft.com . För bättre prestanda bör du använda en server närmast din plats:

- USA: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Storbritannien: api-uk.security.microsoft.com

Token kan erhållas genom åtkomst https://api.security.microsoft.com .

Alla API: er längs `/api` sökvägen använder protokollet [OData](https://docs.microsoft.com/odata/overview) , till exempel https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Komma åt API: erna för skydd mot Microsoft Threat](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
