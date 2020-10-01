---
title: Översikt för Microsoft 365 nätverksanslutning
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365initiative-CoreDeploy
f1.keywords:
- NOCSH
description: I artikeln beskrivs varför nätverks optimering är viktig för SaaS-tjänster, målet för Microsoft 365-nätverk och hur SaaS kräver olika nätverk från andra arbets belastningar.
ms.openlocfilehash: acc55868e47ea89cd2357487838a88032dc8538d
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327491"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Översikt över Microsoft 365-nätverk

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 är ett distribuerat SaaS-moln (program som-as-service) som tillhandahåller produktivitets-och samarbets scenarier via en mängd olika Micro-tjänster och-applikationer. Klient komponenter i Microsoft 365, till exempel Outlook, Word och PowerPoint körs på användare och ansluter till andra komponenter i Microsoft 365 som körs i Microsoft Data Center. Den viktigaste faktorn som avgör kvaliteten på Microsoft 365-slutanvändarens upplevelse är nätverks tillförlitlighet och lång fördröjning mellan Microsoft 365-klienter och Microsoft 365-tjänst front dörrar.

I den här artikeln får du lära dig mer om målen för Microsoft 365-nätverk och varför Microsoft 365-nätverk kräver en annan metod för optimering än allmän Internet trafik.

## <a name="microsoft-365-networking-goals"></a>Mål för Microsoft 365-nätverk

Det ultimata målet för Microsoft 365-nätverk är att optimera slutanvändarens upplevelse genom att aktivera den minst begränsade åtkomsten mellan klienter och de närmaste Microsoft 365-slutpunkterna. Slutanvändarens kvalitet är direkt relaterad till prestanda och svars tid för det program som användaren använder. Till exempel är Microsoft Teams beroende av liten latens så att användare som ringer samtal, konferenser och delade skärmar är felfria och att Outlook är beroende av en bra nätverks anslutning för snabb söknings funktioner som utnyttjar indexerings-och AI-funktioner på Server sidan.

Det primära målet i nätverks utformningen bör vara att minimera fördröjningen genom att minska tiden för cirkulering från klient maskiner till Microsofts globala nätverk, det offentliga nätverks stamnät som sammankopplar Microsoft-datacenters med låga svars tider, med data åtkomst punkter med hög tillgänglighet för att spridas över hela världen. Du kan läsa mer om Microsofts globala nätverk i [Hur Microsoft bygger sitt snabba och tillförlitliga globala nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Optimering av nätverks prestanda för Microsoft 365 behöver inte vara komplicerad. Du får bästa möjliga prestanda genom att följa några viktiga principer:

- Identifiera nätverks trafik i Microsoft 365
- Tillåt att lokal förgrening från Microsoft 365 nätverks trafik till Internet från varje plats där användarna ansluter till Microsoft 365
- Tillåt att Microsoft 365-trafik kringgår utrustning och paket inspektions enheter

Mer information om principer för nätverks anslutningar för Microsoft 365 finns i [principer för nätverks åtkomst för 365](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Traditionella nätverks arkitekturer och SaaS

Principer för traditionell nätverks arkitektur för klient-och Server belastningar är utformade kring antagandet om att trafik mellan klienter och slut punkter inte sträcker sig utanför företagets nätverks gräns. I många företags nätverk är alla utgående Internet anslutningar till företagets nätverk och kommer från en central plats.

I traditionella nätverks arkitekturer måste du ha högre latens för allmän Internet trafik för att upprätthålla nätverkets gräns-och prestanda optimering för Internet trafik, vanligt vis genom att uppgradera eller bygga ut utrustning vid nätverks utgångs punkter. Den här metoden uppfyller emellertid inte kraven för optimal nätverks prestanda hos SaaS-tjänster, till exempel Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identifiera nätverks trafik i Microsoft 365

Vi gör det enklare att identifiera nätverks trafik för Microsoft 365 och göra det enklare att hantera nätverks identifieringen.

- Nya kategorier av nätverks slut punkter för att skilja på mycket kritisk nätverks trafik från nätverks trafik som inte påverkas av Internet fördröjning. Det finns bara en fåtal med URL: er och stöd för IP-adresser i den mest kritiska "optimera"-kategorin.
- Webb tjänster för användning av skript eller direkt enhets konfiguration samt ändrings hantering av Microsoft 365 Network-identifiering. Ändringar är tillgängliga från webb tjänsten eller i RSS-format eller via e-post med hjälp av en Microsoft-arbetsflödesmall.
- [Office 365-nätverks partner program](https://aka.ms/Office365NPP) med Microsoft partners som tillhandahåller enheter eller tjänster som följer Microsofts 365 nätverks anslutnings principer och har enkel konfiguration.

## <a name="securing-microsoft-365-connections"></a>Skydda Microsoft 365-anslutningar

Syftet med den traditionella nätverkssäkerheten är att skärpa företagets nätverksgräns mot intrång och skadlig exploatering. De flesta företags nätverk har nätverks säkerhet för Internet trafik med teknik som proxyservrar, brand väggar, SSL-avbrott och inspektion, djup paket granskning och system för skydd mot data förlust. Dessa tekniker ger viktig riskreducering för allmänna internetförfrågningar, men kan drastiskt minska prestanda, skalbarhet och kvalitet på slutanvändarens upplevelse när den används på slutpunkter för Microsoft 365.

Microsoft 365 hjälper till att möta organisationens behov av säkerhet och data användning med inbyggda säkerhets-och styrnings funktioner avsedda för Microsoft 365-funktioner och arbets belastning. Mer information om säkerhet och efterlevnad för Microsoft 365 finns i [säkerhets översikten för Office 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap). Mer information om Microsofts rekommendationer och support för avancerade nätverks lösningar som utför avancerade funktioner på Microsoft 365-trafik finns i [använda nätverks enheter eller-lösningar från tredje part i Office 365-trafik](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Varför fungerar inte Microsoft 365-nätverk?

Microsoft 365 är utformat för optimal prestanda med slut punkts säkerhet och krypterade nätverks anslutningar, vilket minskar behovet av att skydda perimeternätverket. Microsoft 365-datacenters finns i hela världen och tjänsten är utformad för att använda olika metoder för att ansluta klienter till bästa tillgängliga tjänst slut punkter. Eftersom användar data och bearbetning fördelas mellan många Microsoft-datacenter-finns det ingen nätverks slut punkt som klient datorerna kan ansluta till. I själva verket är data och tjänster i Microsoft 365-klient organisationen optimerade dynamiskt av Microsofts globala nätverk för att anpassa sig till de geografiska platser som de användare får åtkomst till.

Vissa vanliga prestanda problem skapas när Microsoft 365-trafik är föremål för paket granskning och centraliserat utgående:

- Hög latens kan orsaka väldigt dålig prestanda i video-och ljud strömmar och långsamt svar på data hämtning, sökningar, samarbete i real tid, ledig/upptagen-information i produkter, produkt innehåll och andra tjänster
- Utgående anslutningar från en central plats avgränsar funktionerna för dynamisk routning i Microsoft 365 globalt nätverk, att lägga till fördröjning och vänte tid för fördröjningar
- Dekrypterar SSL-skyddad Microsoft 365-nätverks trafik och krypterar den igen kan orsaka protokoll fel och säkerhets risk

Om du förminskar nätverks Sök vägen till Microsoft 365-startadresser genom att låta klient trafik utsättas så nära som möjligt till deras geografiska plats kan prestanda förbättras och slutanvändaren i Microsoft 365. Den kan också bidra till att minska påverkan av framtida ändringar av nätverks arkitekturen på Microsoft 365-prestanda och-pålitlighet. Den optimala anslutnings modellen är att alltid erbjuda att nätverket utsätts på användarens plats, oavsett om det gäller för företagets nätverk eller fjärrplatser, till exempel hem, hotell, kafé och flyg platser. Allmän Internet trafik och WAN-baserad nätverks trafik är separat routad och använder inte den lokala direkt utgångs modellen. Den här lokala direkt utgångsmodellen visas i diagrammet nedan.

![Lokal utgående nätverksarkitektur](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

Den lokala utgångs arkitekturen har följande fördelar för Microsoft 365-nätverks trafik via den traditionella modellen:
  
- Ger optimal Microsoft 365-prestanda genom att optimera väglängden. Slutanvändarens anslutningar dirigeras dynamiskt till den närmaste Microsoft 365-startplatsen av Microsofts globala nätverks _front dörrs_ infrastruktur och trafik dirigeras internt till data-och tjänste slut punkter över Microsoft-fiber högkvalitativt hög tillgänglighet.
- Minskar belastningen på företags infrastrukturen genom att tillåta lokal avslut för Microsoft 365-trafik, förbi proxyservrar och kontroll enheter för trafik.
- Skyddar anslutningar för båda ändarna genom att utnyttja klientens slut punkter för säkerhet och moln, undvika att skydda dig mot redundanta nät verks teknik.

> [!NOTE]
> Infrastrukturen för _distribuerad tjänst front dörren_ är Microsofts globala nätverk med hög tillgänglighet och utbyggbar nätverks kant med geografiskt distribuerade platser. Slut användar anslutningar avbryts och det är effektivt att cirkulera dem inom Microsofts globala nätverk. Du kan läsa mer om Microsofts globala nätverk i [Hur Microsoft bygger sitt snabba och tillförlitliga globala nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Mer information om hur du använder principer för nätverks anslutningar för Microsoft 365 finns i [principer för nätverks åtkomst för 365](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Sammanfattning

Att optimera prestanda för Microsoft 365-nätverk är ett bra sätt att ta bort onödiga hinder. Genom att behandla Microsoft 365-anslutningar som betrodd trafik kan du förhindra att fördröjning införts genom paket granskning och konkurrens för bandbredd. Om du tillåter lokala anslutningar mellan klient datorer och Office 365-slutpunkter aktive ras trafiken dynamiskt via globalt nätverk.

## <a name="related-topics"></a>Relaterade ämnen

[Principer för nätverks åtkomst för Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Utvärdera Microsoft 365 nätverksanslutningar](assessing-network-connectivity.md)

[Nätverksplanering och prestandajustering för Microsoft 365](network-planning-and-performance.md)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)

[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).

[Nätverk för innehållsleverans (CDN)](content-delivery-networks.md)

[Microsoft 365 anslutningstest](https://aka.ms/netonboard)

[Hur Microsoft bygger ett snabbt och tillförlitligt globalt nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 Nätverksbloggen](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
