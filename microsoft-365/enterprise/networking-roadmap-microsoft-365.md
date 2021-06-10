---
title: Nätverksöversikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
description: Översikten för att implementera Microsoft 365 nätverk.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923558"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Nätverksöversikt för Microsoft 365

Microsoft 365 för företag innehåller molntjänster för samarbete och produktivitet, Microsoft Intune och många identitets- och säkerhetstjänster i Microsoft Azure. Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar. Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering. 

En viktig del av din Microsoft 365 registrering är att säkerställa att dina nätverks- och Internetanslutningar är konfigurerade för optimerad åtkomst. Att konfigurera ditt lokala nätverk för att få tillgång till ett globalt distribuerat SaaS-moln (programvara som en tjänst) skiljer sig från ett traditionellt nätverk som är optimerat för trafik till lokala datacenter och en central Internetanslutning. 

Använd de här artiklarna för att förstå de viktigaste skillnaderna och för att ändra dina edge-enheter, klientdatorer och lokala nätverk för att få den bästa prestandan för dina lokala användare.

## <a name="plan"></a>Planera

I planeringsfasen av din nätverksimplementering:

- [Förstå hur Microsoft 365 fungerar](microsoft-365-networking-overview.md)
- [Utvärdera den nuvarande nätverksanslutningen](assessing-network-connectivity.md)
- [Avgöra om ExpressRoute är rätt för din organisation](network-planning-with-expressroute.md)
- [Planera för nätverksenheter](plan-for-network-devices.md)
- [Konfigurera nätverket för migrering](network-and-migration-planning.md)

## <a name="deploy"></a>Distribuera

I distributionsfasen av din nätverksimplementering:

- [Se till att företagsnätverket är optimerat för Microsoft 365 anslutning](set-up-network-for-microsoft-365.md)
- [Lägga till DNS-domänerna för din organisation](../admin/setup/add-domain.md)
- [Optimera anslutningen till Microsoft 365 slutpunkter](microsoft-365-ip-web-service.md)
- [Optimera anslutningen för fjärranslutna medarbetare](microsoft-365-vpn-split-tunnel.md)
- Om det behövs [konfigurerar du ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Hantera

I hanteringsfasen av din nätverksimplementering:

- [Se till att dina nätverksenheter använder de senaste Office 365 slutpunkterna](microsoft-365-endpoints.md)
- [Övervaka och justera nätverksprestanda](network-planning-and-performance.md)
- [Övervaka ExpressRoute-anslutningar](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Leverantörer av nätverksutrustning

Om du är leverantör av nätverksutrustning kan du gå med i [Microsoft 365 Nätverkspartnerprogram](microsoft-365-networking-partner-program.md). Registrera dig för programmet för att bygga Microsoft 365 principer för nätverksanslutning i dina produkter och lösningar. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Hur Contoso nätverkade för Microsoft 365

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

Börja din nätverksplanering med [översikten Microsoft 365 nätverksanslutningar](microsoft-365-networking-overview.md).