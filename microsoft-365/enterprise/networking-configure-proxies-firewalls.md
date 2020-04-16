---
title: 'Steg 4: Konfigurera förbikoppling av trafik'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera webbläsare och gränsenheter för förbikoppling av trafik till betrodda Office 365-platser.
ms.openlocfilehash: b04e16b249dccf8f2461189b8b47abdd252a75d8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504085"
---
# <a name="step-4-configure-traffic-bypass"></a>Steg 4: Konfigurera förbikoppling av trafik

*Det här steget är valfritt och gäller både E3-versionen och E5-versionen av Microsoft 365 Enterprise*

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Eftersom allmän Internettrafik kan utgöra en risk använder företagsnätverk vanligtvis gränsenheter som proxyservrar, SSL-inspektion, paketinspektionsenheter och system för skydd mot dataförlust. Läs om några av problemen med nätverksavlyssningsenheter i [Använda nätverksenheter eller lösningar från tredje part för Office 365-trafik](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

De DNS-domännamn och IP-adresser som används av de molnbaserade tjänsterna i Microsoft 365 är välkända. Dessutom skyddas själva trafiken och tjänsterna med många säkerhetsfunktioner. Eftersom det redan finns skydd på plats behöver dina gränsenheter inte duplicera det. Mellanliggande destinationer och duplicerad säkerhetsbearbetning för Microsoft 365-trafik kan ge dramatiskt försämrade prestanda.

Det första steget för att undvika mellanliggande destinationer och duplicerad säkerhetsbearbetning är att identifiera Microsoft 365-trafik. Microsoft har definierat följande typer av DNS-domännamn och IP-adressintervall, så kallade slutpunkter:

- **Optimera** – Krävs för anslutning till varje Office 365-tjänst och representerar över 75 procent av bandbredden, anslutningarna och datavolymen för Microsoft 365. Dessa slutpunkter representerar Microsoft 365-scenarier som är mest känsliga när det gäller nätverksprestanda, svarstid och tillgänglighet.
- **Tillåt** – Krävs för anslutning till vissa tjänster och funktioner i Microsoft 365, men dessa slutpunkter är inte lika känsliga för nätverksprestanda och svarstider som slutpunkterna i kategorin Optimera.
 - **Standard** – Representerar tjänster och beroenden för Microsoft 365 som inte kräver någon optimering. Du kan hantera slutpunkterna i kategorin Standard som vanlig Internettrafik.

DNS-domännamnen och IP-adressintervallen hittar du på [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

Microsoft rekommenderar att du:

- Använder PAC-skript i webbläsare på lokala datorer för att kringgå dina proxyservrar för DNS-domännamnen för molnbaserade Microsoft 365-tjänster. Mer information om det senaste PAC-skriptet för Microsoft 365 finns i [PowerShell-skriptet Get-Pacfile](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

- Analyserar dina gränsenheter för att ta reda på om det förekommer duplicerad bearbetning och konfigurerar gränsenheterna till att vidarebefordra trafik för att optimera och tillåta slutpunkter utan bearbetning. Detta kallas förbikoppling av trafik. 

Här följer rekommendationer för din nätverksinfrastruktur.

![Rekommendationer för optimering av lokal trafik](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

Gränsenheterna inkluderar brandväggar, SSL-inspektion, paketinspektionsenheter och skydd mot dataförlust. Om du vill konfigurera och uppdatera konfigurationerna för gränsenheter kan du använda ett skript eller ett REST-anrop för att hämta en strukturerad lista med slutpunkter från webbtjänsten för Office 365-slutpunkter. Mer information finns i [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service) (IP-adresser och URL:er för Office 365-webbtjänst).

Observera att du bara kringgår normal proxy och nätverkssäkerhetsbearbetning för trafik till slutpunkterna i kategorin Optimera och Tillåt för Microsoft 365. All annan allmän Internettrafik går via proxy och omfattas av din befintliga nätverkssäkerhetsbearbetning.

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a>Optimera trafik för distansarbetare som använder VPN-anslutningar

Anslutningar för virtuellt privat nätverk (VPN) används vanligtvis av distansarbetare för att få åtkomst till resurser i företagets intranät. En konventionell VPN-anslutning dirigerar ALL trafik, inklusive Internettrafik, till organisationens intranät. Internettrafiken dirigeras till organisationens gränsnätverk och paketbearbetningsenheter. Denna trafik är utsatt för resor och bearbetningsförseningar som märkbart försämrar prestanda och påverkar din arbetstagares produktivitet. 

Uppdelad tunnel är möjligheten för en VPN-anslutning att dirigera angiven trafik via Internet istället för att skicka den via VPN-anslutningen till ditt intranät. Om du vill ha bästa möjliga prestanda för distansarbetare till kritiska Microsoft 365-tjänster som Teams, SharePoint Online och Exchange Online konfigurerar du VPN-anslutningarna med uppdelad tunnel för att skicka trafik för att optimera kategori Office 365-slutpunkter direkt via Internet. 

Detaljerad information finn i [Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step4) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 5](../media/stepnumbers/Step5.png)|[Optimera prestanda för klienten och Office 365-tjänsten](networking-optimize-tcp-performance.md) |



