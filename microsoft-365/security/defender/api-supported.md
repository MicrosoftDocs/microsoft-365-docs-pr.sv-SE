---
title: Microsoft 365 Defender API:er som stöds
description: Microsoft 365 Defender API:er som stöds
keywords: Microsoft 365 Defender API:er, api
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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985090"
---
# <a name="supported-microsoft-365-defender-apis"></a>Microsoft 365 Defender API:er som stöds 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="list-of-available-apis"></a>Lista över tillgängliga API:er

Artikel | Beskrivning
-|-
[Avancerad jakt-API](api-advanced-hunting.md) | Kör avancerade frågor för sökning.
[API:er för tillbud](api-incident.md) | Lista och uppdatera incidenter, tillsammans med andra praktiska uppgifter.
[Direktuppspelnings-API](streaming-api.md) (förhandsversion) | Leverera händelser och aviseringar i realtid när de inträffar i en enda dataström.

### <a name="endpoint-uris"></a>Slutpunkts-URI:er

Bas-URI för båda de viktigaste API:erna är: https://api.security.microsoft.com . Du kan använda en server närmare din geolokalisering för bättre prestanda:

- USA: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Storbritannien: api-uk.security.microsoft.com

Token kan köpas genom https://api.security.microsoft.com åtkomst.

Alla API:er längs sökvägen använder till exempel `/api` [OData-protokollet.](/odata/overview) https://api.security.microsoft.com/api/incidents

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Defender API:er – översikt](api-overview.md)
- [Få åtkomst Microsoft 365 Defender API:er](api-access.md)
- [API för direktuppspelning](../defender-endpoint/raw-data-export.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
