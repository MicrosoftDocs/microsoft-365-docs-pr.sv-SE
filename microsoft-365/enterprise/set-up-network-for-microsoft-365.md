---
title: Konfigurera ditt nätverk för Microsoft 365
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
description: Hitta länkar till artiklar med information som hjälper dig att konfigurera ditt nätverk för Microsoft 365, inklusive en översikt över nätverks anslutningen och en lista med slut punkter.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694376"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Konfigurera ditt nätverk för Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

En viktig del av din Microsoft 365-registrering är att kontrol lera att nätverks-och Internet anslutningarna är konfigurerade för optimerad åtkomst. Att konfigurera det lokala nätverket för att få åtkomst till ett globalt distribuerat program som-som-as-service-moln är inte samma som ett traditionellt nätverk som är optimerat för trafik till lokala data Center och en central Internet anslutning. 

Använd dessa artiklar för att förstå de viktigaste skillnaderna och för att ändra dina gräns enheter, klient datorer och lokala nätverk för att få bästa möjliga prestanda för dina lokala användare.

## <a name="how-microsoft-365-networking-works"></a>Så fungerar Microsoft 365-nätverk

De här artiklarna visar en översikt över anslutnings barhet för Microsoft 365:

- [Översikt över Microsoft 365-nätverk](microsoft-365-networking-overview.md)
- [Principer för nätverks åtkomst för Microsoft 365](microsoft-365-network-connectivity-principles.md)
- [Utvärderar Microsoft 365-nätverksanslutningar](assessing-network-connectivity.md)

Råd om hur du förbättrar prestanda finns i [nätverks planering och prestanda justering för Microsoft 365](network-planning-and-performance.md).

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Hantera Microsoft 365-nätverk som nätverks utrustnings leverantör

Om du är nätverks utrustning kan du gå med i [Office 365 Network partner-programmet](microsoft-365-networking-partner-program.md). Registrera programmet för att skapa principer för Office 365-nätverks anslutningar till dina produkter och lösningar. 

## <a name="office-365-endpoints"></a>Slut punkter för Office 365

Slut punkter är den uppsättning mål-IP-adresser, DNS-domännamn och URL: er för Office 365-trafik på Internet. 

För att optimera prestanda i Office 365-molnbaserade tjänster behöver vissa slut punkter särskild hantering av dina klient webbläsare och enheter i ditt nätverk. Dessa enheter inkluderar brand väggar, SSL-avbrotts-och inspektions enheter samt system för skydd mot data förlust.

Mer information finns i [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md) .

Det finns fem olika Office 365-moln. I den här tabellen går du till listan med slut punkter för var och en av dem.

| Slut punkter | Beskrivning |
|:-------|:-----|
| [Slut punkter för hela världen](urls-and-ip-address-ranges.md) | Slut punkter för Office 365-prenumerationer, som omfattar Förenta staternas regerings community-moln (GCC). |
| [Amerikanska myndigheters DoD slut punkter](microsoft-365-u-s-government-dod-endpoints.md) | Slut punkter för abonnemang med DoD för Förenta staternas försvar (departementet). |
| [Amerikanska myndigheters GCC höga slut punkter](microsoft-365-u-s-government-gcc-high-endpoints.md) | Slut punkterna för de samhälls omfattande community-molnen (GCC hög). |
| [Office 365 som drivs av 21Vianet-slutpunkter](urls-and-ip-address-ranges-21vianet.md) | Slut punkter för Office 365 som drivs av 21Vianet, som är avsedda att möta behoven hos Office 365 i Kina. |
| [Office 365 Germany-slut punkter](microsoft-365-germany-endpoints.md) | Slut punkterna för ett separat moln i Europa för de mest reglerade kunderna i Tyskland, Europeiska unionen (EU) och Europeiska fri handels associationen (EFTA). |
|||

Information om hur du hämtar den senaste listan över slut punkter för Office 365-molnet finns i [office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md).

Ytterligare slut punkter finns i följande artiklar:

- [Ytterligare slut punkter som inte ingår i webb tjänsten](additional-office365-ip-addresses-and-urls.md)
- [Nätverks begär anden i Office 2016 för Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Ytterligare avsnitt för Microsoft 365-nätverk

De här artiklarna innehåller specialiserade ämnen i Microsoft 365-nätverk:

- [Nätverk för innehålls leverans](content-delivery-networks.md)
- [IPv6-stöd i Office 365-tjänster](ipv6-support.md)
- [Stöd för NAT med Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute för Microsoft 365

Se de här artiklarna för att få information om hur du använder ExpressRoute för Office 365-trafik:

- [Azure ExpressRoute för Office 365](azure-expressroute.md)
- [Implementera ExpressRoute för Office 365](implementing-expressroute.md)
- [Nätverks planering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
- [Routning med ExpressRoute för Office 365](routing-with-expressroute.md)
