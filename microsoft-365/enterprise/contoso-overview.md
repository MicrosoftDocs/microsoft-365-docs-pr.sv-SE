---
title: Översikt över Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå företaget Contoso Corporation och dess hela struktur.
ms.openlocfilehash: b0c00ed5657d914851f28278a2f4cf80660b53b0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754274"
---
# <a name="overview-of-contoso-corporation"></a>Översikt över Contoso Corporation

Contoso Corporation är ett multinationellt företag som har sitt huvudkontor i Paris. Företaget är en tillverknings-, försäljnings- och supportorganisation med fler än 100 000 produkter.

## <a name="contoso-around-the-world"></a>Contoso runtom i världen

Bild 1 visar huvudkontoret i Paris och regionala nav- och satellitkontor på olika världsdelar.

![Contoso-kontor över hela världen](../media/contoso-overview/contoso-overview-fig1.png)

**Bild 1: Contoso-kontor över hela världen**
 
Contoso har tre nivåer av kontor:

- Huvudkontor

  Contosos huvudkontor är ett företags campus i paris med dussintals byggnader för administrations-, teknik- och tillverkningsanläggning. Alla Contoso-datacenter och dess internetnärvaro finns på huvudkontoret i Paris.

  Huvudkontoret har 25 000 medarbetare.

- Regionala nav

  Navkontor har en specifik region i världen med 60 procents försäljning och supportpersonal. Varje regionalt nav är anslutet till Paris huvudkontor via en WAN-länk med hög bandbredd.

  De regionala naven har i genomsnitt 2 000 anställda.

- Satellitkontor

  Satellitkontor innehåller försäljning på 80 procent och supportpersonal. De tillhandahåller närvaro på plats för Contoso-kunder i viktiga städer eller underregion. Varje satellitkontor är anslutet till ett regionalt nav via en WAN-länk med hög bandbredd.

  Satellitkontoren har i genomsnitt 250 anställda.

Cirka 25 procent av Contoso-personalstyrkan är endast mobil. De regionala naven och satellitkontoren har en högre procentandel av dessa medarbetare. Att erbjuda bättre support för mobila arbetare är ett viktigt affärsmål för Contoso.

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>Designöverväganden för Microsoft 365 för företag

Contoso IT-arkitekter har identifierat följande designkravfaktorer för att distribuera Microsoft 365 för företag:

- Flera geografiska platser med lokala regler och efterföljandekrav
- Ett centralt intranätdatacenter på huvudkontorets kontors- och regionala programservrar som fungerar som värd för interna affärsprogram
- En befintlig infrastruktur för Microsoft Endpoint Configuration Manager
- En blandning av klientdatorenheter som kör Windows, Mac och Linux
- En blandning av personliga och företagsspecifika mobila enheter, bland annat iOS (iPhone och iPad), telefoner och surfplattor med Android
- Många distansarbete och mycket mobil personal
- Många företagspartner
- En stor mängd privat kundinformation och annan konfidentiell information som ska hanteras och säkras
- En stor mängd immaterialrätt med högt värde i form av utformningsspecifikationer för produkter och tillverkningsaffärshemligheter

## <a name="next-step"></a>Nästa steg

Läs mer om Contoso Corporations lokala [IT-infrastruktur](contoso-infra-needs.md) och hur företagets affärsbehov hanteras med Microsoft 365 för företag.

## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
