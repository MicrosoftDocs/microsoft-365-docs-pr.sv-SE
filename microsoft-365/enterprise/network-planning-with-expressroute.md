---
title: Nätverks planering med ExpressRoute för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: I den här artikeln får du lära dig mer om Azure ExpressRoute för Office 365 och hur du använder det för nätverks planering.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694634"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Nätverks planering med ExpressRoute för Office 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med ExpressRoute för Office 365 får du nivå 3-anslutning mellan nätverket och Microsofts Data Center. Kretsarna använder BGP-vägar (Border Gateway Protocol) för Office 365-frontend-servrar. Från perspektivet på dina lokala enheter när de måste välja rätt TCP/IP-sökväg till Office 365 visas Azure ExpressRoute som ett alternativ till Internet.
  
Azure ExpressRoute lägger till en direkt sökväg till en specifik uppsättning funktioner som stöds och tjänster som erbjuds av Office 365-servrar i Microsofts Data Center. Azure ExpressRoute ersätter inte Internet anslutningen till Microsoft-datacenters eller grundläggande Internet tjänster, till exempel domän namns matchning. Azure ExpressRoute och dina Internet kretsar bör vara säkra och överflödiga.
  
I följande tabell beskrivs några skillnader mellan Internet-och Azure ExpressRoute-anslutningar i kontexten för Office 365.

|**Skillnader i nätverks planering**|**Internet nätverks anslutning**|**ExpressRoute nätverks anslutning**|
|:-----|:-----|:-----|
| Till gång till Internet tjänster, inklusive;  <br/>  DNS-namnmatchning  <br/>  Verifiering av certifikat återkallning  <br/>  Innehålls leverans nätverk (CDN)  <br/> |Ja  <br/> |Förfrågningar till Microsoft-ägda DNS-och/eller CDN-infrastrukturer kan använda ExpressRoute nätverk.  <br/> |
| Till gång till Office 365-tjänster, inklusive;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype för företag – Online  <br/>  Office i en webbläsare  <br/>  Office 365-portal och-verifikation  <br/> |Ja, alla program och funktioner  <br/> |Ja, [specifika program och funktioner](https://aka.ms/o365endpoints) <br/> |
|Lokal säkerhet vid perimeter.  <br/> |Ja  <br/> |Ja  <br/> |
|Planering för hög tillgänglighet.  <br/> |Redundans till en alternativ Internet nätverks anslutning  <br/> |Redundans till en alternativ ExpressRoute-anslutning  <br/> |
|Direkt anslutning med en förutsägbar nätverks profil.  <br/> |Nej  <br/> |Ja  <br/> |
|IPv6-anslutning.  <br/> |Ja  <br/> |Ja  <br/> |

Expandera rubrikerna nedan för mer information om nätverks planering. Vi har också spelat in en 10-part [för Azure ExpressRoute för Office 365-utbildning](https://channel9.msdn.com/series/aer) som Dives djupare.

## <a name="existing-azure-expressroute-customers"></a>Befintliga Azure ExpressRoute-kunder

Om du använder en befintlig Azure ExpressRoute-krets och vill lägga till Office 365-anslutning via den här kretsen bör du titta på antalet kretsar, utgångs platser och deras storlek för att uppfylla behoven hos din Office 365-användning. De flesta kunder kräver mer bandbredd och många kräver ytterligare kretsar.
  
Om du vill aktivera åtkomst till Office 365 över dina befintliga Azure ExpressRoute-kretsar [konfigurerar du väg filtren](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) så att Office 365-tjänsterna är tillgängliga.
  
Azure ExpressRoute-prenumerationen är kundinriktad, vilket innebär att abonnemang är knutna till kunder. Som kund kan du ha flera Azure ExpressRoute-kretsar och kan komma åt många Microsoft Cloud-resurser via dessa kretsar. Du kan till exempel välja att få till gång till en virtuell Azure-dator, en Office 365 test-klient och en klient organisation för Office 365 som har ett par redundanta Azure ExpressRoute-kretsar.
  
Den här tabellen beskriver de två typerna av peering-relationer som du kan välja för att implementera dina kretsar.

|**Peering-relation**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Uthyrning** <br/> |IaaS: virtuella Azure-datorer  <br/> |PaaS: offentliga Azure-tjänster  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Anslutnings initiering * * * * <br/> |Kund till Microsoft  <br/> Microsoft-till-kund  <br/> |Kund till Microsoft  <br/> Microsoft-till-kund  <br/> |
|**QoS-support** <br/> |Ingen QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> Endast QoS stöder Skype för företag för närvarande.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Bandbredds planering för Azure ExpressRoute

Alla Office 365-kunder har unika bandbredds behov beroende på antalet personer på varje plats, hur aktivt de är med varje Office 365-program och andra faktorer som användning av lokala och hybrid utrustning samt konfigurationer för nätverks säkerhet.
  
Om du har för lite bandbredd kan det leda till överbelastning, återöverföringar av data och oväntade fördröjningar. Om du har för mycket bandbredd kommer onödiga kostnader att uppstå. I ett befintligt nätverk kallas bandbredd ofta för att det finns tillräckligt med ledigt utrymme på kretsen som procents ATS. Om du har 10 procents utrymme kommer det troligen att leda till överbelastning och att 80%-utrymme inte är onödigt kostnad. Tilldelningar för typiska utrymme är 20% till 50%.
  
För att hitta rätt bandbredd kan du testa din befintliga nätverks användning. Det är det enda sättet att få ett sant mått på användningen och behovet av nätverks konfiguration och program vara på något sätt som är unikt. När du mäter dig vill du verkligen vara uppmärksam på den totala bandbredds förbrukning, fördröjning och TCP-överbelastning för att förstå dina nätverks behov.
  
När du har en uppskattad original plan som inkluderar alla nätverks program, pilot kontor 365 med en liten grupp som omfattar olika profiler för personer i organisationen för att fastställa faktisk användning och använda de två mätningarna för att uppskatta den bandbredd du behöver för varje Office-plats. Om det finns några problem med fördröjningar eller TCP-överbelastningar i din testning kan du behöva flytta utgångs numret närmare de personer som använder Office 365 eller ta bort intensiv nätverks genomsökning såsom SSL-dekryptering/kontroll.
  
Alla rekommendationer om vilken typ av nätverks bearbetning som rekommenderas gäller för både ExpressRoute och Internet kretsar. Detsamma gäller för resten av vägledningen på vår [webbplats för prestanda justering](https://aka.ms/tune).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Använda säkerhets kontroller i Azure ExpressRoute för Office 365-scenarier

Att skydda Azure ExpressRoute-anslutningen börjar med samma principer som att skydda Internet anslutningen. Många kunder väljer att distribuera nätverks-och perimeter-kontroller längs ExpressRoute-sökvägen som ansluter sitt lokala nätverk till Office 365 och andra Microsoft-moln. Dessa kontroller kan inkludera brand väggar, programproxyservrar, förhindrande av data läckage, intrång, intrångs skydd och så vidare. I många fall tillämpar kunderna olika nivåer av kontroller för trafik som initieras från lokal telefon till Microsoft, och trafik som initieras från Microsoft till kundens lokala nätverk, och trafik som initieras från lokal telefon till en allmän Internet destination.
  
Här är några exempel på hur du integrerar säkerheten med [ExpressRoute anslutnings modell](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) som du väljer att distribuera.

|**Integrerings alternativ för ExpressRoute**|**Perimeternätverksgränssnitt för nätverks säkerhet**|
|:-----|:-----|
|Co-finns i ett moln utbyte  <br/> |Installera ny eller Använd befintlig infrastruktur för säkerhets-/perimeter i den gemensamma platsen där ExpressRoute-anslutningen är etablerad.  <br/> Utnyttja Co-location enbart för routning/sammanlänkning och backend-anslutningar från Co-location till den lokala säkerhets-/perimeter infrastrukturen.  <br/> |
|Point-to-Point-Ethernet  <br/> |Avsluta Point-to-Point-ExpressRoute i den befintliga lokala säkerhets-/gräns infrastruktur platsen.  <br/> Installera ny säkerhets-/perimeter-infrastruktur som är specifik för ExpressRoute-sökvägen och avsluta Point-to-point-anslutningen där.  <br/> |
|Valfri-till-ett IPVPN  <br/> |Använda en befintlig lokal säkerhets-/perimeter-infrastruktur på alla platser som ingår i IPVPN som används för ExpressRoute för Office 365-anslutning.  <br/> Fäst IPVPN som används för ExpressRoute för Office 365 till specifika lokala platser som är avsedda att fungera som säkerhet/perimeter.  <br/> |

Vissa tjänste leverantörer erbjuder även hanterade säkerhets-/perimeter-funktioner som en del av deras integrerings lösningar med Azure ExpressRoute.
  
När du funderar på hur topologin för nätverks-och säkerhets alternativ används för ExpressRoute för Office 365-anslutningar, följer du de här aspekterna
  
- Nätverks-och säkerhets kontroller för djup och typ kan påverka prestanda och skalbarhet för Office 365-gränssnittet.

- Utgående (lokala- \> Microsoft) och inkommande (Microsoft- \> lokalt) [om aktiverat] flöden kan ha andra krav. Dessa skiljer sig från utgående till allmänna Internet destinationer.

- Kraven på Office 365 för portar/protokoll och nödvändiga IP-undernät är desamma om trafik dirigeras via ExpressRoute för Office 365 eller via Internet.

- TOPY-placering av kundens nätverks-och säkerhets kontroller avgör det ultimata slutdatumet för slutanvändaren för användare och Office 365-tjänsten och kan ha en avsevärd inverkan på nätverks fördröjning och överbelastning.

- Kunder uppmuntras att utforma sin säkerhets-/perimeter-topologi för användning med ExpressRoute för Office 365 i enlighet med metod tips för redundans, hög tillgänglighet och katastrof återställning.

Här är ett exempel på Sparbanken som jämför de olika Azure ExpressRoute-anslutnings alternativen med de perimeter-och gräns säkerhets modellerna ovan.
  
### <a name="example-1-securing-azure-expressroute"></a>Exempel 1: skydda Azure ExpressRoute
  
Sparbanken funderar på att implementera Azure ExpressRoute och när du har planerat den optimala arkitekturen för [routning med ExpressRoute för Office 365](routing-with-expressroute.md) och när du har använt ovanstående vägledning för att förstå kraven på bandbredden bestämmer de de bästa metoderna för att skydda sin perimeter.
  
För sparbanker och organisationer med flera kontinenter måste säkerheten omfatta alla perimeter. Det optimala anslutnings alternativet för Sparbank är en flervals förbindelse med flera peering-platser världen över för att hantera behoven hos sina anställda i varje kontinent. Varje kontinent innehåller redundanta Azure ExpressRoute-kretsar inom kontinenten och säkerheten måste omfatta alla dessa.
  
Sparbankens befintliga infrastruktur är pålitlig och kan hantera det ytterligare arbetet, till exempel Sparbanken kan använda infrastrukturen för sin Azure ExpressRoute och Internet-perimeter. Om så inte är fallet kan Sparbanken välja att köpa ytterligare utrustning för att komplettera sin befintliga utrustning eller för att hantera en annan typ av anslutning.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hög tillgänglighet och redundans med Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Vi rekommenderar att du etablerar minst två aktiva kretsar från varje utgång med ExpressRoute till din ExpressRoute-leverantör. Det här är det vanligaste sättet vi ser fel för kunder och du enkelt kan undvika det genom att etablera ett par aktiva/aktiva ExpressRoute kretsar. Vi rekommenderar även minst två aktiva/aktiva Internet kretsar eftersom många Office 365-tjänster endast är tillgängliga via Internet.
  
Inuti utgångs punkten för ditt nätverk är många andra enheter och kretsar som spelar en avgörande roll när det gäller tillgänglighet. Dessa delar av dina anslutnings scenarier är inte täckta av ExpressRoute eller Office 365 SLAs, men de spelar en viktig roll i syfte att få slut på tjänst tillgängligheten från personer i organisationen.
  
Fokus på de personer som använder och arbetar med Office 365, om ett fel i en komponent skulle påverka folks upplevelse med tjänsten, leta efter olika sätt att begränsa den totala procent andelen av personer som påverkas. Om ett failover-läge fungerar som det ska, bör du överväga de personer som har en lång tid att återställa och leta efter utförda enkla och automatiserade växlings lägen.
  
Utanför ditt nätverk har Office 365, ExpressRoute och ExpressRoute-leverantören olika tillgänglighets nivåer.
  
### <a name="service-availability"></a>Tjänst tillgänglighet
  
- Office 365-tjänster täcks av väldefinierade [service nivå avtal](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)som inkluderar drifts-och tillgänglighets mått för enskilda tjänster. En orsak till att Office 365 kan hantera sådana höga tillgänglighets nivåer är möjligheten för enskilda komponenter att sömlöst redundansväxla mellan de många Microsoft-datacenters, med hjälp av det globala Microsoft-nätverket. Denna redundans sträcker sig från data Center och nätverket till flera avgångs punkter för Internet, och aktiverar failover sömlöst från de personer som använder tjänsten.

- ExpressRoute [ger 99,9% tillgänglighet SLA](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) för enskilda dedikerade kretsar mellan Microsofts nätverks Edge och ExpressRoute-leverantören eller partner infrastrukturen. Dessa tjänst nivåer tillämpas på ExpressRoute-kretsen, som består av [två oberoende sammankopplade anslutningar](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) mellan den redundanta Microsoft-utrustningen och nät leverantörs utrustningen på varje peering-plats.

### <a name="provider-availability"></a>Leverantörs tillgänglighet
  
- Microsofts Service nivå arrangemang stannar hos din ExpressRoute-leverantör eller-partner. Det här är också första gången du kan göra val som påverkar din tillgänglighets nivå. Du bör noggrant utvärdera egenskaperna för arkitektur, tillgänglighet och återhämtning som din ExpressRoute-leverantör erbjuder mellan din nätverks gräns och din leverantörs anslutning på varje Microsoft-peering-plats. Var uppmärksam på både logiska och fysiska aspekter av redundans, peering Equipment, bärvåg tillhandahålls WAN-kretsar och eventuella ytterligare värden Lägg till tjänster som NAT-tjänster eller hanterade brand väggar.

### <a name="designing-your-availability-plan"></a>Designa din tillgänglighets plan
  
Vi rekommenderar starkt att du planerar och utformar hög tillgänglighet och återhämtning till slutanvändarnas scenarier för Office 365. En konstruktion bör omfatta;
  
- inga enskilda fel punkter, inklusive både Internet-och ExpressRoute kretsar.

- minimera antalet personer som påverkas och varaktigheten av denna påverkan för de mest förutsedda fel lägena.

- optimering för enkel, upprepnings bar och automatisk återställning från de mest förutsedda fel lägena.

- stöd för nätverks trafikens och funktionalitetens fulla behov via redundanta vägar, utan avsevärd försämring.

Dina anslutnings scenarier bör omfatta en nätverkstopologi som är optimerad för flera oberoende och aktiva nätverks Sök vägar till Office 365. Detta ger en bättre tillgänglighet från slut punkt till slut punkt än en topologi som endast optimeras för redundans på enskilda enheter eller utrustnings nivåer.
  
> [!TIP]
> Om dina användare fördelas över flera kontinenter eller geografiska regioner och var och en av dessa platser ansluter via redundanta WAN-kretsar till en enda lokal plats där en enda ExpressRoute-krets finns, kommer användarna att få mindre heltäckande tjänst tillgänglighet än en nätverks Topology-design som innehåller oberoende ExpressRoute-kretsar som ansluter de olika regionerna till närmaste peering-plats.
  
Vi rekommenderar att du etablerar minst två ExpressRoute kretsar med varje krets som ansluter till med en annan geografisk peering-plats. Du bör etablera det här aktiva paret kretsar för varje region där folk ska använda ExpressRoute-anslutningen för Office 365-tjänster. Detta gör att varje region kan vara ansluten under en katastrof som påverkar en viktig plats, till exempel ett Data Center eller en peering-plats. Genom att konfigurera dem som aktiva/aktiva kan slutanvändarens trafik distribueras över flera olika nätverks Sök vägar. Detta minskar omfattningen av de personer som påverkas under enhets-eller nätverks utrustningen.
  
Vi rekommenderar inte att du använder en enda ExpressRoute-krets med Internet som en säkerhets kopia.
  
### <a name="example-2-failover-and-high-availability"></a>Exempel 2: redundans och hög tillgänglighet
  
Sparbankens multi-geografisk design har genomgått en recension av routning, bandbredd, säkerhet och nu måste du gå igenom en recension med hög tillgänglighet. Sparbanken vill ha hög tillgänglighet som täcker tre kategorier; återhämtning, pålitlighet och redundans.
  
Återhämtning gör att Sparbanken inte kan komma igång snabbt. Med tillförlitlighet kan Sparbanken ge ett enhetligt resultat i systemet. Redundans gör att Sparbanken kan flyttas mellan en eller flera speglade instanser av infrastrukturen.
  
Inom varje Edge-konfiguration har Sparbanken vissa brand väggar, proxyservrar och ID: n. För Nord Amerika har Sparbanken en Edge-konfiguration i sitt Borås-datacenter och en annan Edge-konfiguration i ett Virginia-datacenter. Den redundanta utrustningen på varje plats erbjuder återhämtning till den platsen.
  
Nätverks konfigurationen på Sparbanken bygger på några viktiga principer:
  
- Inom varje geografiskt område finns det flera Azure ExpressRoute-kretsar.

- Varje krets inom en region kan stödja all nätverks trafik inom det området.

- Operationsföljden kan tydligt föredra en eller flera andra Sök vägar beroende på tillgänglighet, plats och så vidare.

- Redundans mellan Azure ExpressRoute-kretsar sker automatiskt utan ytterligare konfiguration eller åtgärd enligt Sparbanken.

- Redundans mellan Internet kretsar sker automatiskt utan ytterligare konfiguration eller åtgärd enligt Sparbanken.

I denna konfiguration, med redundans på fysisk och virtuell nivå, kan Sparbanken ge lokal återhämtning, regional återhämtning och global återhämtning på ett säkert sätt. Sparbank valde denna konfiguration efter utvärdering av en enda Azure ExpressRoute-krets per region samt möjligheten att gå över till Internet.
  
Om Sparbanken inte kunde ha flera Azure ExpressRoute-kretsar per region skulle trafik med ursprung i Nord Amerika till Azure ExpressRoute-kretsen i Asien Stilla havs området lägga till en oacceptabel fördröjnings nivå och nödvändig DNS forwarding-konfiguration ökar komplexiteten.
  
Vi rekommenderar inte att du använder Internet som säkerhets kopierings konfiguration. Detta bryter sin Tillförlitlighets princip, vilket resulterar i en inkonsekvent upplevelse med anslutningen. Dessutom krävs manuell konfiguration för redundansväxling med den BGP-annonsering som har kon figurer ATS, NAT-konfiguration, DNS-konfiguration och proxykonfigurationen. Detta ökar tiden för att återställa och minska möjligheten att diagnosticera och felsöka stegen.
  
Har du fortfarande frågor om hur du planerar för och implementerar Traffic Management eller Azure ExpressRoute? Läs resten av vår [nätverks-och prestanda råd](https://aka.ms/tune) eller [vanliga frågor om Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).
  
## <a name="working-with-azure-expressroute-providers"></a>Arbeta med Azure ExpressRoute-leverantörer
<a name="BKMK_high-availability"> </a>

Välj plats för dina kretsar baserat på din bandbredd, svars tid, säkerhet och planering för hög tillgänglighet. När du vet att de platser du vill använda kretsar i kan du [läsa igenom den aktuella listan med leverantörer efter region](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Arbeta med din leverantör eller dina providrar för att välja bästa anslutnings alternativ, en punkt till punkt, flera punkter eller värd. Kom ihåg att du kan mixa och matcha anslutnings alternativen så länge bandbredden och andra överflödiga komponenter har stöd för Routning och hög tillgänglighet.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
## <a name="related-topics"></a>Närliggande ämnen
<a name="BKMK_high-availability"> </a>

[Utvärdering av Office 365 nätverks anslutning](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365](managing-expressroute-for-connectivity.md)
  
[Routning med ExpressRoute för Office 365](routing-with-expressroute.md)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Använda BGP-communities i ExpressRoute för Office 365](bgp-communities-in-expressroute.md)
  
[Media kvalitet och nätverks anslutnings prestanda i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimera ditt nätverk för Skype för företag – Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute och QoS i Skype för företag – Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtals flöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Prestanda justering för Office 365 med bas linjer och prestanda historik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md)
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-nätverks-och prestanda inställning](network-planning-and-performance.md)
  
[Vanliga frågor om Office 365-slut punkter](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
