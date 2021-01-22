---
title: 'Microsoft 365 Defender API: er som stöds'
description: 'Microsoft 365 Defender API: er som stöds'
keywords: MTP, API:er, api
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
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926204"
---
# <a name="supported-microsoft-365-defender-apis"></a>Microsoft 365 Defender API: er som stöds 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="list-of-available-apis"></a>Lista över tillgängliga API:er

Artikel | Beskrivning
-|-
[Advanced jakt-API](api-advanced-hunting.md) | Köra Avancerade frågor om sökfrågor.
[API:er för tillbud](api-incident.md) | Lista och uppdatera incidenter, tillsammans med andra praktiska uppgifter.

### <a name="endpoint-uris"></a>Slutpunkts-URI:er

Bas-URI för båda de viktigaste API:erna är: https://api.security.microsoft.com . Använd en server närmare din geolokalisering för bättre prestanda:

- USA: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Storbritannien: api-uk.security.microsoft.com

Token kan köpas genom https://api.security.microsoft.com åtkomst.

Alla API:er längs vägen använder till exempel `/api` [OData-protokollet.](https://docs.microsoft.com/odata/overview) https://api.security.microsoft.com/api/incidents

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över API:er för Microsoft 365 Defender](api-overview.md)
- [Få åtkomst till API:er för Microsoft Threat Protection](api-access.md)
- [Läs mer om API-begränsningar och -licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
