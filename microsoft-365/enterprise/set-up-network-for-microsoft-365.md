---
title: Konfigurera nätverket för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Hitta länkar till artiklar med information som hjälper dig att konfigurera nätverket för Microsoft 365, inklusive en översikt över nätverksanslutningen och en lista över slutpunkter.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694376"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Konfigurera nätverket för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

En viktig del av Microsoft 365 är att se till att nätverks- och Internetanslutningar är konfigurerade för optimerad åtkomst. Att konfigurera ditt lokala nätverk för att få tillgång till ett globalt distribuerat SaaS-moln (programvara som en tjänst) skiljer sig från ett traditionellt nätverk som är optimerat för trafik till lokala datacenter och en central Internetanslutning. 

Använd de här artiklarna för att förstå de viktigaste skillnaderna och för att ändra dina edge-enheter, klientdatorer och lokala nätverk för att få den bästa prestandan för dina lokala användare.

## <a name="how-microsoft-365-networking-works"></a>Så här Microsoft 365 nätverk fungerar

I de här artiklarna finns en översikt över anslutning för Microsoft 365:

- [Översikt för Microsoft 365 nätverksanslutning](microsoft-365-networking-overview.md)
- [Microsoft 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)
- [Utvärdera Microsoft 365 nätverksanslutningar](assessing-network-connectivity.md)

Råd om förbättring av prestanda finns i [Nätverksplanering och prestandajustering för Microsoft 365.](network-planning-and-performance.md)

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Stöd Microsoft 365 nätverk som leverantör av nätverksutrustning

Om du är leverantör av nätverksutrustning ansluter du till [Office 365 Nätverkspartnerprogram](microsoft-365-networking-partner-program.md). Registrera dig för programmet för att bygga Office 365 principer för nätverksanslutning i dina produkter och lösningar. 

## <a name="office-365-endpoints"></a>Office 365-slutpunkter

Slutpunkter är en uppsättning IP-måladresser, DNS-domännamn och URL:er för Office 365 trafik på Internet. 

För att optimera prestanda Office 365 av molnbaserade tjänster behöver vissa slutpunkter särskild hantering av dina klientwebbläsare och enheter i ditt gränsnätverk. Dessa enheter omfattar brandväggar, SSL-avbrott, inspektera och paketinspektionsenheter samt system för skydd mot dataförlust.

Mer [information Office 365 hantera slutpunkter.](managing-office-365-endpoints.md)

Det finns för närvarande fem Office 365 moln. Den här tabellen tar dig till listan med slutpunkter för var och en.

| Slutpunkter | Beskrivning |
|:-------|:-----|
| [Globala slutpunkter](urls-and-ip-address-ranges.md) | Slutpunkterna för globala Office 365 prenumerationer, som omfattar USA och Government Community Cloud (GCC). |
| [Slutpunkter för Myndighetsskydd i USA](microsoft-365-u-s-government-dod-endpoints.md) | Slutpunkterna för United States Department of Defense-prenumerationer (DoD). |
| [Slutpunkter för Myndighetsskydd i USA (GCC High)](microsoft-365-u-s-government-gcc-high-endpoints.md) | Slutpunkterna för prenumerationer med Government Community Cloud Hög (GCC Hög). |
| [Office 365 som drivs av 21Vianet – Slutpunkter](urls-and-ip-address-ranges-21vianet.md) | Slutpunkterna för Office 365 som drivs av 21Vianet, som är utformade för att tillgodose behoven Office 365 i Kina. |
| [Slutpunkter för Office 365 Germany](microsoft-365-germany-endpoints.md) | Slutpunkterna för ett separat moln i Europa för de kunder i Tyskland, Europeiska unionen (EU) och EES (European Free Trade Association) som regleras mest. |
|||

Information om hur du automatiserar hur du hämtar den senaste listan med slutpunkter för Office 365-molnet finns [i Office 365 IP-adress och URL-webbtjänst.](microsoft-365-ip-web-service.md)

Fler slutpunkter finns i följande artiklar:

- [Ytterligare slutpunkter som inte ingår i webbtjänsten](additional-office365-ip-addresses-and-urls.md)
- [Nätverksbegäranden i Office 2016 för Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Ytterligare ämnen för Microsoft 365 nätverk

Läs följande artiklar för specialiserade ämnen Microsoft 365 nätverk:

- [Nätverk för innehållsleverans](content-delivery-networks.md)
- [IPv6-stöd i Office 365-tjänster](ipv6-support.md)
- [Stöd för NAT med Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute för Microsoft 365

Läs följande artiklar för information om hur du använder ExpressRoute för Office 365 trafik:

- [Azure ExpressRoute för Office 365](azure-expressroute.md)
- [Implementera ExpressRoute för Office 365](implementing-expressroute.md)
- [Nätverksplanering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
- [Dirigering med ExpressRoute för Office 365](routing-with-expressroute.md)
