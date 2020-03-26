---
title: 'Fas 1: Avslutsvillkor för nätverksinfrastruktur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise-villkoren för nätverksinfrastruktur.
ms.openlocfilehash: 1ace68fd19c62e4dc389604c1b0c02ddc18b52dc
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42807489"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a>Fas 1: Avslutsvillkor för nätverksinfrastruktur

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Kontrollera att nätverksinfrastrukturen uppfyller följande krav och att du har övervägt de som är valfria.

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Obligatoriskt: Ditt nätverk är redo för Microsoft 365 Enterprise

- Dina kontor har tillräcklig internetbandbredd för Microsoft 365-trafik, t. ex. installationer och uppdateringar av Office 365, Microsoft Intune och Windows 10 Enterprise.
- Ditt nätverk är kartlagt i en [Office 365 Reference Architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).
- Din nätverksändringar har övervakats och testats och uppfyller dina krav gällande trafikfördröjning.

Vid behov kan [Steg 1](networking-provide-bandwidth-cloud-services.md) hjälpa dig med detta krav.

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Obligatoriskt: De lokala kontoren har lokala internetanslutningar och namnmatchning

Du har konfigurerat varje lokalt kontor med internetåtkomst via en lokal internetleverantör vars DNS-servrar använder en lokal, publik IP-adress som identifierar deras plats på internet. Detta säkerställer bästa möjliga prestanda för användare av Microsoft 365-molntjänster.

Om du inte använder en lokal internetleverantör för varje filial kan prestandan bli lidande då nätverkstrafiken måste korsa företagets stamnät, eller också hanteras dataförfrågningar av fjärrservrar.

### <a name="how-to-test"></a>Så testar man
Använd ett verktyg eller en webbplats från en enhet i det kontoret för att avgöra den publika IP-adress som proxyservern använder. Använd till exempel webbplatsen [What Is My IP Address](https://www.whatismypublicip.com/). Den publika IP-adress som tilldelats dig av internetleverantören bör vara geografiskt lokal. Den ska inte vara från ett offentligt IP-adressintervall för ett centralt kontor eller en molnbaserad leverantör av nätverkssäkerhet.

Vid behov kan [Steg 2](networking-dns-resolution-same-location.md) hjälpa dig med detta krav.

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a>Valfritt: onödiga nätverkshairpins tas bort

Du har undersökt nätverkets hairpins och fastställt effekten på prestandan för alla dina kontor. Du har tagit bort hårnålar i nätverket där det är möjligt eller arbetat med ditt nätverk från tredje part eller säkerhetsleverantören för att implementera optimal Microsoft 365-peering för deras nätverk.

Vid behov kan [Steg 3](networking-avoid-network-hairpins.md) hjälpa dig med detta alternativ.


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Valfritt: Du har konfigurerat förbikoppling av trafik på dina webbläsare och edge-enheter

De senaste PAC-filerna har distribuerats i dina lokala webbläsare så att trafik till Microsoft 365 DNS-domännamn förbigår proxyservrar.

You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.


### <a name="how-to-test"></a>Så testar man

Använd loggningsverktygen på nätverkets kringliggande enheter för att säkerställa att trafik till Microsoft 365-destinationer inte kontrolleras, dekrypteras eller på annat sätt förhindras.

Vid behov kan [Steg 4](networking-configure-proxies-firewalls.md) hjälpa dig med detta alternativ.


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Valfritt: Dina klienter och Office 365-appar är konfigurerade för optimala prestanda

Du har optimerat TCP-inställningarna (Transmission Control Protocol) på dina klientenheter och för Exchange Online, Skype för företag – Online, SharePoint Online och Microsoft Project Online-tjänster.

Vid behov kan [Steg 5](networking-optimize-tcp-performance.md) hjälpa dig med detta alternativ.

## <a name="results-and-next-steps"></a>Resultat och nästa steg

Dina intranätanvändare är nu redo att använda Microsoft 365-molntjänster via en effektiv nätverksväg till och på internet.

|||
|:-------|:-----|
|![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)| Om du följer stegen för slutpunkt till slutpunkt-distribution av Microsoft 365 Enterprise, är nästa fas [identitet](identity-infrastructure.md). |
