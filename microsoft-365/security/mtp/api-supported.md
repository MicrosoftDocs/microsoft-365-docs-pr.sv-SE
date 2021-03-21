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
ms.openlocfilehash: a162226793cc63a9e7e4d490c721a2c488ac64fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922180"
---
# <a name="supported-microsoft-365-defender-apis"></a>Microsoft 365 Defender API: er som stöds 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information handlar om en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="list-of-available-apis"></a>Lista över tillgängliga API:er

Artikel | Beskrivning
-|-
[Advanced jakt-API](api-advanced-hunting.md) | Kör avancerade frågor för sökning.
[API:er för tillbud](api-incident.md) | Lista och uppdatera incidenter, tillsammans med andra praktiska uppgifter.

### <a name="endpoint-uris"></a>Slutpunkts-URI:er

Bas-URI för båda de viktigaste API:erna är: https://api.security.microsoft.com . Du kan använda en server närmare din geolokalisering för bättre prestanda:

- USA: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Storbritannien: api-uk.security.microsoft.com

Token kan köpas genom https://api.security.microsoft.com åtkomst.

Alla API:er längs sökvägen använder till exempel `/api` [OData-protokollet.](/odata/overview) https://api.security.microsoft.com/api/incidents

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender-API:er](api-overview.md)
- [Åtkomst till API:er för Microsoft Threat Protection](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)