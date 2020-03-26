---
title: 'Steg 2: Konfigurera lokala internetanslutningar för varje kontor'
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
description: Förstå och konfigurera DNS-upplösningen för bättre prestanda.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806024"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Steg 2: Konfigurera lokala internetanslutningar för varje kontor

*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

I steg 2 ser du till att alla dina kontor har lokala Internet-anslutningar och använder lokala DNS-servrar. Båda dessa element är nödvändiga för att minska anslutningsfördröjningen och se till att lokala klientdatorer ansluter till närmaste molnbaserade Microsoft 365-tjänster.

I traditionella nätverk för stora organisationer sänds Internet-trafik via nätverksstamnätet till en central Internet-anslutning. Det här fungerar inte bra för att optimera prestanda för en global distribuerad Saas-infrastruktur (programvara som tjänst), som omfattar Office 365- och Intune-produkter i Microsoft 365.

Microsofts globala nätverk innehåller en *distribuerad Front Door Service*-infrastruktur, en nätverksgräns med hög tillgänglighet som är mycket skalbar med geografiskt distribuerade platser. Den avslutar användarens anslutningar på en Front Door-server och dirigerar effektivt slutanvändarens trafik i Microsofts globala nätverk.

![Microsofts globala nätverk](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

För bästa prestanda ska lokala klienter komma åt en plats som ligger geografiskt närmast, i stället för att trafiken skickas via ett nätverksstamnät och till den startpunkt (front door) som ligger närmast organisationens centrala Internet-anslutning.

Här följer ett exempel.

![Exempel på användning av Microsofts globala nätverk](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

När en användare på det lokala kontoret i Paris vill få åtkomst till en SharePoint Online-webbplats:

1. Den skickar en DNS-fråga för att matcha ett namn, t. ex. contoso.sharepoint.com. 
2. Den DNS-server som tillhandahålls av Internet-leverantören vidarebefordrar den frågan till en Microsoft DNS-server.
3. Microsofts DNS-servrar matchar käll-IP-adressen för den vidarebefordrade DNS-frågan till den region i världen som tilldelats adressen. Microsofts DNS-server svarar med IP-adressen för den närmaste Microsoft-nätverksanslutningen i Europa.
4. Internet-leverantörens DNS-server skickar IP-adressen till användaren.
5. Användaren upprättar en anslutning till SharePoint-servern via Europas startpunkt.

Om du vill dirigera en klientbegäran till en startpunkt som är närmast geografiskt använder Microsofts DNS-servrar DNS-frågorna som motsvarar klientens första anslutningsbegäran. För att få lägsta möjliga nätverksfördröjning ska:

- Alla kontor i din organisation ha lokala Internet-anslutningar för att [optimera](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) kategorin för nätverkstrafik.
- Varje lokal Internet-anslutning ska använda en regional lokal DNS-server för utgående Internet-trafik från den platsen.

Mer information finns i [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally) (Utgående lokala nätverksanslutningar). 

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step2) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)|[Undvika nätverkshairpins](networking-avoid-network-hairpins.md)|
