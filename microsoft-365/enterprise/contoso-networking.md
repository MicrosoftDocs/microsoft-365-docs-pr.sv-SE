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
description: Förstå nätverks infrastrukturen contoso och hur företaget använder sin SD-WAN-teknik för optimal nätverks prestanda till Microsoft 365 för företags moln tjänster.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754020"
---
# <a name="networking-for-the-contoso-corporation"></a>Nätverk för Contoso Corporation

För att kunna använda molnbaserade infrastrukturer har Contoso en grundläggande skift på hur nätverks trafik till moln tjänster flyttas. I stället för en intern modell för nav-och-eker som fokuserar på nätverks anslutning och trafik för nästa nivå i Office-hierarkin, mappas användarna till lokala Internet-avslut-och lokala anslutningar till den närmaste Microsoft 365-nätverks platsen på Internet.

## <a name="networking-infrastructure"></a>Nätverks infrastruktur

Det här är nätverks element som länkar contoso-kontor över hela världen:

- MPLS-WAN-nätverk

  Ett MPLS WAN-nätverk ansluter Paris till lokala kontor och lokala kontor till satellit kontor i en konfiguration med ekrar och nav. Nätverket gör att användare kan komma åt lokala servrar som bildar branschspecifika tillämpningar i Paris-kontoret. Den dirigerar också all allmän Internet trafik till Paris kontoret, där nätverks säkerhetsenheterna sveper på begäran. Inom varje kontor levererar routrar trafik till trådanslutna och trådlösa åtkomstpunkter i undernät, som använder det privata IP-adressutrymmet.

- Lokal direkt Internet åtkomst för Microsoft 365-trafik

  Varje Office har en programdefinierad WAN-enhet (SD-WAN) med en eller flera lokala Internet-nätkretsar med sin egen Internet anslutning via en proxyserver. Lösningen implementeras vanligtvis som en WAN-länk till en lokal Internetleverantör, som även tillhandahåller offentliga IP-adresser och en lokal DNS-server.

- Internet-närvaro

  Contoso äger det contoso \. com offentlige-domännamnet. Den offentliga contoso-webbplatsen för att beställa produkter är en uppsättning servrar i ett Internet-anslutet Data Center i Paris campus. Contoso använder ett/24 offentliga IP-adressintervall på Internet.

Bild 1 visar nätverks infrastrukturen contoso och dess anslutningar till Internet.

![Contoso-nätverket](../media/contoso-networking/contoso-networking-fig1.png)
 
**Bild 1: Contoso-nätverket**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Användning av SD-WAN för optimal nätverksanslutning till Microsoft

Contoso följde [principerna för nätverksanslutningar för Microsoft 365](microsoft-365-network-connectivity-principles.md) för att:

- Identifiera och särskilja Microsoft 365-nätverkstrafik
- Utgående nätverksanslutningar lokalt
- Undvika nätverkshairpins
- Kringgå dubblerade enheter för nätverkssäkerhet

Det finns tre kategorier av nätverks trafik för Microsoft 365: *optimera*, *tillåta*och *standard*. Optimera och tillåta trafik är betrodd nätverks trafik som krypteras och skyddas på slut punkterna och är avsedd för Microsoft 365-nätverket.

Contoso fattade beslutet att:

- Använd direkt Internet avslut för att optimera och tillåta kategori trafik och vidarebefordra all standard kategori trafik till den Paris centrala Internet anslutningen.

- Distribuera SD-WAN-enheter på varje kontor för att enkelt kunna följa dessa principer och uppnå optimal nätverks prestanda för Microsoft 365-molnbaserade tjänster.

  SD-WAN-enheterna har en LAN-port för det lokala kontorsnätverket och flera WAN-portar. En WAN-port ansluter till deras MPLS-nätverk. En annan ansluter till en lokal Internet-leverantör. SD-WAN-enheten dirigerar nätverkstrafik i kategorierna Optimera och Tillåt via Internetleverantörslänken.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Program infrastrukturen contoso line of Business

Contoso har utformat sin infrastruktur för program och Server intranät för följande:

- Satellitkontor använder lokala cache-servrar för att lagra dokument som används ofta och interna webbplatser.
- Regionala nav använder regionala programservrar för region- och satellitkontor. Servrarna synkroniseras med servrar på huvudkontoret i Paris.
- Paris Campus-datacentren innehåller centraliserade program servrar som tjänar hela organisationen.

Bild 2 visar hur stor andel av nätverks trafiken som används vid åtkomst till servrar i Contoso-intranätet.

![Contoso-infrastrukturen för interna program](../media/contoso-networking/contoso-networking-fig2.png)
 
**Bild 2: contoso-infrastrukturen för interna program**

För satellit-eller regionala Hubbs kontoret kan 60 procent av de resurser som behövs av de anställda betjänas via satellit-och regionala hubb kontor. Ytterligare 40 procent av resurs begär Anden måste gå via WAN-länken till Paris campus.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Nätverks analys och förberedelse för Microsoft 365 för företag

Om du har godkänt Microsoft 365 för företags tjänster av Skype-användare beror det på hög tillgänglighet och anslutning till Internet eller direkt till Microsofts moln tjänster. Contoso vidtog de här stegen för att planera och implementera optimerad anslutning till Microsoft 365 för företags moln tjänster:

1. Skapa ett nätverks diagram för företagets WAN till stöd för planering

   För att kunna starta sin nätverks planering skapar Contoso ett diagram som visar deras Office-platser, befintliga nätverks anslutningar, befintliga nätverks gränser och tjänste klasser som hanteras i nätverket. De använde diagrammet för varje efterföljande steg under planering och implementering av nätverksanslutningen.

2. Skapa ett abonnemang för Microsoft 365 för företags nätverks anslutning

   Contoso använde [principer för nätverks anslutningen för microsoft 365](microsoft-365-network-connectivity-principles.md) och exempel referens nätverks arkitektur för att identifiera SD-WAN som sin bästa topologi för Microsoft 365-anslutningen.

3. Analysera Internet-anslutnings användning och MPLS – WAN-bandbredd för varje kontor och öka bandbredden efter behov

   Varje Office-nuvarande användning analyserades och kretsarna har ökats så att den förutsedda Microsoft 365-molnbaserade trafiken skulle fungera med en genomsnittlig oanvänd kapacitet på 20 procent.

4. Optimera prestandan till Microsofts nätverks tjänster

   Contoso har fastställt uppsättningen av Office 365-, Intune-och Azure-slutpunkter samt konfigurerade brand väggar, säkerhetsenheter och andra system i Internet-sökvägen för optimal prestanda. Slut punkter för Office 365 optimera och Tillåt att kategori trafik konfigurerades till SD-WAN-enheter för routning via Internet-kretsen.

5. Konfigurera intern DNS

   DNS måste fungera och letas upp lokalt för Microsoft 365-trafik.

6. Verifiera nätverks slut punkten och port anslutningar

   Contoso körde test verktyg för Microsoft Network connectivity för att verifiera anslutningen för Microsoft 365 för företags moln tjänster.

7. Optimera datorns datorer för nätverks anslutningar

   Enskilda datorer markerades för att se till att de senaste operativ system uppdateringarna installerades och att övervakning av slut punkts säkerhet var aktivt för alla klienter.

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso använder [sin lokala Active Directory Domain Services i molnet](contoso-identity.md) för anställda och federering för kunder och affärs partners.

## <a name="see-also"></a>Se även

[Nätverks översikt för Microsoft 365](networking-roadmap-microsoft-365.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
