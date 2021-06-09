---
title: Nätverk för Contoso Corporation
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
description: Förstå Contoso-nätverksinfrastrukturen och hur företaget använder sin SD-WAN-teknik för optimala nätverksprestanda för att Microsoft 365 företagmolntjänster.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754020"
---
# <a name="networking-for-the-contoso-corporation"></a>Nätverk för Contoso Corporation

För att införa en molnomfattande infrastruktur har Contoso utformat ett grundläggande skift för hur nätverkstrafik till molntjänster färdas. I stället för en intern modell med hub-and-ekrar som fokuserar nätverksanslutning och trafik för nästa nivå av Office-hierarkin mappade de användarplatser till lokal internetpunkt och lokala anslutningar till närmaste Microsoft 365-nätverksplats på internet.

## <a name="networking-infrastructure"></a>Nätverksinfrastruktur

Det här är de nätverkselement som kopplar samman Contosos kontor över hela världen:

- MPLS-WAN-nätverk

  Ett MPLS WAN-nätverk ansluter Paris huvudkontor till regionala kontor och regionala kontor till satellitkontor i en ek-och-hubb-konfiguration. Nätverket gör det möjligt för användare att få åtkomst till lokala servrar som består av affärsprogram i huvudkontoret i Paris. Den dirigerar även all allmän internettrafik till Paris kontor, där nätverkssäkerhetsenheter skrubbar förfrågningarna. Inom varje kontor levererar routrar trafik till trådanslutna och trådlösa åtkomstpunkter i undernät, som använder det privata IP-adressutrymmet.

- Lokal direkt internetanslutning för Microsoft 365 trafik

  Varje kontor har en programvarudefinierad WAN-enhet (WAN) som har en eller flera lokala internetnätverkskretsar via Internet via en proxyserver. Lösningen implementeras vanligtvis som en WAN-länk till en lokal Internetleverantör, som även tillhandahåller offentliga IP-adresser och en lokal DNS-server.

- Internet-närvaro

  Contoso äger det offentliga domännamnet contoso \. com. Den offentliga Contoso-webbplatsen för produktorder är en uppsättning servrar i ett internetanslutet datacenter i Paris campus. Contoso använder ett /24 offentligt IP-adressintervall på Internet.

Bild 1 visar Contosos nätverksinfrastruktur och dess anslutningar till Internet.

![Contoso-nätverket](../media/contoso-networking/contoso-networking-fig1.png)
 
**Bild 1: Contoso-nätverket**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Användning av SD-WAN för optimal nätverksanslutning till Microsoft

Contoso följde [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) för att:

- Identifiera och särskilja Microsoft 365-nätverkstrafik
- Utgående nätverksanslutningar lokalt
- Undvika nätverkshairpins
- Kringgå dubblerade enheter för nätverkssäkerhet

Det finns tre kategorier av nätverkstrafik för Microsoft 365: *Optimera,* *Tillåt* och *Standard.* Optimera och tillåt trafik är betrodd nätverkstrafik som är krypterad och säker på slutpunkterna och är avsedd för det Microsoft 365 nätverket.

Contoso fattade beslutet att:

- Använd direkt utgående Internet för optimera och tillåt kategoritrafik och för att vidarebefordra all standardkategoritrafik till den parisbaserade centrala Internetanslutningen.

- Distribuera SD-WAN-enheter på varje kontor som ett enkelt sätt att följa de här principerna och få optimala nätverksprestanda för Microsoft 365 molnbaserade tjänster.

  SD-WAN-enheterna har en LAN-port för det lokala kontorsnätverket och flera WAN-portar. En WAN-port ansluter till sitt MPLS-nätverk. En annan ansluter till en lokal ISP-krets. SD-WAN-enheten dirigerar nätverkstrafik i kategorierna Optimera och Tillåt via Internetleverantörslänken.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Infrastrukturen för appen Contoso-affärsprogrammet

Contoso har byggt sin infrastruktur för branschprogram och server intranät för följande:

- Satellitkontor använder lokala cache-servrar för att lagra dokument som används ofta och interna webbplatser.
- Regionala nav använder regionala programservrar för region- och satellitkontor. Servrarna synkroniseras med servrar på huvudkontoret i Paris.
- Datacenter i Paris campus innehåller centraliserade programservrar som används av hela organisationen.

I bild 2 visas den procentandel av nätverkskapaciteten som används vid åtkomst av servrar i Contoso-intranätet.

![Contoso-infrastrukturen för interna program](../media/contoso-networking/contoso-networking-fig2.png)
 
**Bild 2: Contoso-infrastrukturen för interna program**

För satellit- eller regionala navkontor kan 60 procent av de anställdas resurser användas av satellit- och regionala navkontorsservrar. Ytterligare 40 procent av resursförfrågningarna måste gå över WAN-länken till Paris campus.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Nätverksanalys och förberedelse inför Microsoft 365 för företag

Ett lyckat införande Microsoft 365 företagstjänster av Contoso-användare är beroende av att Contoso-användarna är tillgängliga och är uppkopplade direkt till Internet eller direkt till Microsofts molntjänster. Contoso har gjort följande för att planera och implementera optimerad anslutning för Microsoft 365 för molntjänster för företag:

1. Skapa ett företags WAN-nätverksdiagram för planering

   Contoso började sin nätverksplanering genom att skapa ett diagram som visar deras kontorsplatser, befintliga nätverksanslutningar, befintliga perimeterenheter för nätverket och klasser för tjänster som hanteras i nätverket. De använde diagrammet för varje efterföljande steg under planering och implementering av nätverksanslutningen.

2. Skapa en plan för Microsoft 365 för företagsnätverksanslutningar

   Contoso använde [Microsoft 365](microsoft-365-network-connectivity-principles.md) principer för nätverksanslutning och nätverksarkitekturer för exempelreferenser för att identifiera SD-WAN som primär topologi för Microsoft 365 anslutning.

3. Analysera användningen av Internetanslutning och MPLS-WAN-bandbredd på varje kontor, och öka bandbredden vid behov

   Varje kontors aktuella användning analyserades och kretsarna utökades så att förutsägelsen Microsoft 365 molnbaserad trafik skulle fungera med i genomsnitt 20 procents oanvänd kapacitet.

4. Optimera prestanda för Microsofts nätverkstjänster

   Contoso bestämde uppsättningen Office 365, Intune och Azure-slutpunkter och konfigurerade brandväggar, säkerhetsenheter och andra system i Internetsökvägen för optimala prestanda. Slutpunkter för Office 365 optimera och tillåt kategoritrafik konfigurerades i SD-WAN-enheter för dirigering över ISP-kretsen.

5. Konfigurera intern DNS

   DNS måste fungera och letas upp lokalt för Microsoft 365-trafik.

6. Validera nätverksslutpunkt och portanslutning

   Contoso körde testverktygen för Microsoft-nätverksanslutning för att validera Microsoft 365 för företagmolntjänster.

7. Optimera nätverksanslutningar för anställdas datorer

   Enskilda datorer har kontrollerats för att säkerställa att de senaste uppdateringarna av operativsystemet installerades och att säkerhetsövervakning av slutpunkten var aktiv på alla klienter.

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso utnyttjar sina lokala [Active Directory Domain Services](contoso-identity.md) i molnet för anställda och federera autentisering för kunder och affärspartner.

## <a name="see-also"></a>Se även

[Nätverksöversikt för Microsoft 365](networking-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
