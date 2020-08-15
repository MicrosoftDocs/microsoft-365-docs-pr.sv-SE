---
title: Nätverks översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Översikten för implementering av Microsoft 365-nätverk.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694612"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Nätverks översikt för Microsoft 365

Microsoft 365 för företag innehåller samarbets-och produktivitets moln tjänster, Microsoft Intune och många identitets-och säkerhets tjänster i Microsoft Azure. Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar. Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering. 

En viktig del av din Microsoft 365-registrering är att kontrol lera att nätverks-och Internet anslutningarna är konfigurerade för optimerad åtkomst. Att konfigurera det lokala nätverket för att få åtkomst till ett globalt distribuerat program som-som-as-service-moln är inte samma som ett traditionellt nätverk som är optimerat för trafik till lokala data Center och en central Internet anslutning. 

Använd dessa artiklar för att förstå de viktigaste skillnaderna och för att ändra dina gräns enheter, klient datorer och lokala nätverk för att få bästa möjliga prestanda för dina lokala användare.

## <a name="plan"></a>Planera

Under planerings fasen av nätverks implementeringen:

- [Förstå hur Microsoft 365-nätverk fungerar](microsoft-365-networking-overview.md)
- [Bedöma din aktuella nätverks anslutning](assessing-network-connectivity.md)
- [Avgöra om ExpressRoute passar din organisation](network-planning-with-expressroute.md)
- [Planera för nätverks enheter](plan-for-network-devices.md)
- [Konfigurera nätverks inställningar för migrering](network-and-migration-planning.md)

## <a name="deploy"></a>Distribuera

I distributions fasen av nätverks implementeringen:

- [Kontrol lera att ditt företags nätverk är optimerat för Microsoft 365-anslutning](set-up-network-for-microsoft-365.md)
- [Lägga till DNS-domäner för din organisation](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Optimera anslutningen till Microsoft 365-slutpunkter](microsoft-365-ip-web-service.md)
- [Optimera anslutningen för fjärranställda](microsoft-365-vpn-split-tunnel.md)
- Om det behövs [konfigurerar du ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Hantera

I hanterings fasen av nätverks implementeringen:

- [Kontrol lera att dina nätverks enheter använder de senaste Office 365-slutpunkterna](microsoft-365-endpoints.md)
- [Övervaka och justera nätverks prestanda](network-planning-and-performance.md)
- [Övervaka dina ExpressRoute-anslutningar](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Leverantörer av nätverks utrustning

Om du är nätverks utrustning kan du gå med i [Microsoft 365 Network partner-programmet](microsoft-365-networking-partner-program.md). Registrera dig för att skapa Microsoft 365-nätverks anslutnings principer till produkterna och lösningarna. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Så här fungerade contoso för Microsoft 365

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

Starta Nätverks planering med [Översikt över Microsoft 365-nätverksanslutningen](microsoft-365-networking-overview.md).
