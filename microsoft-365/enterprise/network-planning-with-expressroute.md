---
title: Nätverksplanering med ExpressRoute för Office 365
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
description: I den här artikeln får du lära dig mer om Azure ExpressRoute för Office 365 och hur du använder det för nätverksplanering.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923582"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Nätverksplanering med ExpressRoute för Office 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

ExpressRoute för Office 365 tillhandahåller anslutningar i det tredje lagret mellan ditt nätverk och Microsofts datacenter. Kretsarna använder BGP-ruttannonsering (Border Gateway Protocol) av Office 365-frontend-servrarna. Utifrån dina lokala enheters perspektiv ses Azure ExpressRoute som ett alternativ till Internet när de behöver välja rätt TCP/IP-sökväg till Office 365.
  
Azure ExpressRoute tillhandahåller en direkt rutt till en specifik uppsättning funktioner och tjänster som stöds och tillhandahålls av Office 365-servrar i Microsofts datacenter. Azure ExpressRoute ersätter inte internetanslutningen till Microsoft-datacenter eller grundläggande internettjänster som namnmatchning för domäner. Azure ExpressRoute och dina internetkretsar ska vara säkrade och redundanta.
  
I följande tabell visas några skillnader mellan internet- och Azure ExpressRoute-anslutningar i samband med Office 365.

|**Skillnader i nätverksplanering**|**Internetanslutning**|**ExpressRoute-nätverksanslutning**|
|:-----|:-----|:-----|
| Åtkomst till nödvändiga internettjänster, inklusive:  <br/>  DNS-namnmatchning  <br/>  Certifikatåterkallningsverifiering  <br/>  Content Delivery Networks (CDN)  <br/> |Ja  <br/> |Förfrågningar till Microsoft-ägd DNS- och/eller CDN-infrastruktur kan använda ExpressRoute-nätverket.  <br/> |
| Åtkomst till Office 365-tjänster, inklusive:  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype för företag online  <br/>  Office i en webbläsare  <br/>  Office 365- portal och autentisering  <br/> |Ja, alla program och funktioner  <br/> |Ja, [vissa program och funktioner](./urls-and-ip-address-ranges.md) <br/> |
|Lokal säkerhet vid perimeter.  <br/> |Ja  <br/> |Ja  <br/> |
|Planering för hög tillgänglighet.  <br/> |Redundans för en alternativ Internetanslutning  <br/> |Redundans för en alternativ ExpressRoute-anslutning  <br/> |
|Direkt anslutning med en förutsägbar nätverksprofil.  <br/> |Nej  <br/> |Ja  <br/> |
|IPv6-anslutning.  <br/> |Ja  <br/> |Ja  <br/> |

Expandera rubrikerna nedan för mer vägledning för nätverksplanering. Vi har även spelat in en 10-delar [lång Azure ExpressRoute för Office 365-utbildningsserie](https://channel9.msdn.com/series/aer) som dyker djupare.

## <a name="existing-azure-expressroute-customers"></a>Befintliga Azure ExpressRoute-kunder

Om du använder en befintlig Azure ExpressRoute-krets och vill lägga till Office 365-anslutningar över den här kretsen bör du titta på antalet kretsar, egressplatser och storleken på kretsarna för att säkerställa att de uppfyller behoven för din Office 365-användning. De flesta kunder behöver ytterligare bandbredd och många kräver ytterligare kretsar.
  
För att ge åtkomst till Office 365 genom [](/azure/expressroute/how-to-routefilter-portal) dina befintliga Azure ExpressRoute-kretsar konfigurerar du routefiltren för att säkerställa att Office 365-tjänsterna är tillgängliga.
  
Azure ExpressRoute-prenumerationen är kundcentrerad, vilket innebär att abonnemang är knutna till kunder. Som kund kan du ha flera Azure ExpressRoute-kretsar och kan komma åt många Microsoft-molnresurser genom dessa kretsar. Du kan till exempel välja att komma åt en virtuell Azure-dator, en Office 365-testklientorganisation och en Office 365-produktionsklientorganisation genom ett par redundanta Azure ExpressRoute-kretsar.
  
I den här tabellen beskrivs de två typer av peeringrelationer som du kan välja att implementera över dina kretsar.

|**Peeringrelation**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Tjänster** <br/> |IaaS: Virtuella Azure-datorer  <br/> |PaaS: Offentliga Azure-tjänster  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Initiering av anslutning**** <br/> |Kund till Microsoft  <br/> Microsoft till kund  <br/> |Kund till Microsoft  <br/> Microsoft till kund  <br/> |
|**QoS-support** <br/> |Ingen QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS har endast stöd för Skype för företag för närvarande.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planering av bandbredd för Azure ExpressRoute

Varje Office 365-kund har unika bandbreddsbehov beroende på antalet personer på varje plats, hur aktiva de är med varje Office 365-program och andra faktorer som användning av lokal eller hybridutrustning och nätverkssäkerhetskonfigurationer.
  
För lite bandbredd resulterar i överbelastning, data som måste måste vidareöveras och oförutsägbara fördröjningar. För mycket bandbredd innebär en onödig kostnad. På ett befintligt nätverk refereras det till bandbredd som tillgängligt utrymme i kretsen i procent. 10 % utrymme kommer troligen att resultera i överbelastning, och 80 % utrymme innebär vanligtvis en onödig kostnad. Vanliga utrymmesmålallokeringar är 20 till 50 %.
  
För att hitta rätt bandbreddsnivå är det bästa sättet att testa den befintliga nätverksanvändningen. Det här är det enda sättet att få ett verkligt mått på användningen och behov eftersom alla nätverkskonfigurationer och -program på vissa sätt är unika. När du mäter är det bra att vara uppmärksam på den totala bandbreddsanvändningen, svarstiden och TCP-överbelastningen för att förstå dina nätverksbehov.
  
När du har ett uppskattat basvärde som inkluderar alla nätverksprogram pilottestar du Office 365 med en liten grupp med olika användarprofiler i organisationen för att fastställa den faktiska användningen och använder de två måtten för att uppskatta hur mycket bandbredd du kommer att behöva för varje kontorsplats. Om det finns problem med fördröjning eller TCP-överbelastning som påträffas under testningen kan du behöva flytta den utgående anslutningen närmare de som använder Office 365 eller ta bort resurskrävande nätverksskanning som SSL-dekryptering/kontroll.
  
Alla våra rekommendationer om vilken typ av nätverksbearbetning som rekommenderas gäller för både ExpressRoute- och Internetkretsar. Samma sak gäller för resten av vägledningen på vår [prestandajusteringswebbplats](./network-planning-and-performance.md).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Använda säkerhetskontroller på Azure ExpressRoute för Office 365-scenarier

Skydd av Azure ExpressRoute-anslutningar börjar med samma principer som för att skydda internetanslutningen. Många kunder väljer att distribuera nätverks- och perimeterkontroller längs ExpressRoute-vägen som ansluter deras lokala nätverk till Office 365 och andra Microsoft-moln. Dessa kontroller kan omfatta brandväggar, programproxier, skydd mot dataläckor, intrångsidentifiering, skyddssystem mot intrång och så vidare. I många fall använder kunder olika nivåer av kontroller på trafik initierad från en lokal plats till Microsoft, kontra trafik initierad från Microsoft till kundens lokala nätverk, kontra trafik initierad från den lokala platsen till en allmän Internetdestination.
  
Här är några exempel på integrering av säkerhet med [ExpressRoute-anslutningsmodellen som](/azure/expressroute/expressroute-connectivity-models) du väljer att distribuera.

|**Alternativ för ExpressRoute-integrering**|**Perimetermodell för nätverkssäkerhet**|
|:-----|:-----|
|Samreliger på en molnbaserad exchange  <br/> |Installera ny eller utnyttja befintlig säkerhets- och perimeterinfrastruktur i samplatsplatsen där ExpressRoute-anslutningen upprättas.  <br/> Använd samplatsplatsen enbart för dirigering/samkoppling och dra anslutningar tillbaka från samplatsplatsen till den lokala säkerhets- och perimeterinfrastrukturen.  <br/> |
|Punkt till punkt-Ethernet  <br/> |Avsluta Punkt till punkt-anslutningen på den befintliga platsen för den lokala säkerhets- och perimeterinfrastrukturen.  <br/> Installera den nya säkerhets- och perimeterinfrastrukturen som är specifik för ExpressRoute-sökvägen och avsluta Punkt till punkt-anslutningen där.  <br/> |
|Any-to-Any IPVPN  <br/> |Utnyttja en befintlig lokal säkerhets- och perimeterinfrastruktur på alla platser som egress till det IPVPN som används för ExpressRoute för Office 365-anslutningar.  <br/> Fästa det IPVPN som används för ExpressRoute för Office 365 till specifika lokala platser avsedda att fungera som säkerhet/perimeter.  <br/> |

Vissa tjänsteleverantörer erbjuder även hanterade säkerhets- och perimeterfunktioner som en del av sina integrationslösningar med Azure ExpressRoute.
  
Här följer ytterligare överväganden när du överväger topologiplaceringen av nätverks- och säkerhets perimeteralternativen som används för ExpressRoute för Office 365-anslutningar
  
- Djup och typ av nätverks- och säkerhetskontroller kan påverka prestanda och skalbarheten för Office 365-användarupplevelsen.

- Utgående (lokalt - \> Microsoft) och inkommande (Microsoft- \> on-premises) [om aktiverat] flöden kan ha olika krav. Dessa är sannolikt annorlunda än Utgående till allmänna Internetdestinationer.

- Office 365-kraven för portar/protokoll och nödvändiga IP-undernät är desamma oavsett om trafiken dirigeras via ExpressRoute för Office 365 eller via Internet.

- Den topologiska placeringen av kundens nätverks- och säkerhetskontroller avgör det slutgiltiga end to end-nätverket mellan användaren och Office 365-tjänsten och kan ha en betydande inverkan på nätverkets fördröjning och överbelastning.

- Kunderna uppmanas att utforma sin säkerhets- och perimetertopologi för användning med ExpressRoute för Office 365 enligt rekommendationer för redundans, hög tillgänglighet och återställning vid katastrof.

Här är ett exempel på Woodgrove Bank som jämför de olika Azure ExpressRoute-anslutningsalternativen med de perimetersäkerhetsmodeller som nämns ovan.
  
### <a name="example-1-securing-azure-expressroute"></a>Exempel 1: Skydda Azure ExpressRoute
  
Woodgrove Bank överväger att implementera Azure ExpressRoute. Efter att ha planerat den optimala arkitekturen för dirigering med ExpressRoute för [Office 365](routing-with-expressroute.md) och använt ovanstående vägledning för att förstå bandbreddskraven fastställer de den bästa metoden för att skydda sin perimeter.
  
För Woodgrove, ett multinationellt företag på flera världsdelar, måste säkerheten omfatta alla perimeterdelar. Det optimala anslutningsalternativet för Woodgrove är en flerpunktsanslutning med flera peeringplatser runt världen för de anställdas behov på varje världsdel. Varje världsdel har redundanta Azure ExpressRoute-kretsar och säkerheten måste omfatta alla dessa.
  
Woodgroves befintliga infrastruktur är tillförlitlig och kan hantera det ytterligare arbetet. Woodgrove Bank kan därför använda infrastrukturen för sin Azure ExpressRoute- och internet perimetersäkerhet. Om så inte vore fallet skulle Woodgrove välja att köpa ytterligare utrustning för att komplettera sin befintliga utrustning eller hantera en annan typ av anslutning.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hög tillgänglighet och redundans med Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Vi rekommenderar att du etablerar minst två aktiva kretsar från varje utgång med ExpressRoute till din ExpressRoute-leverantör. Det här är den vanligaste platsen vi ser fel för kunder och du kan enkelt undvika det genom att etablera ett par aktiva/aktiva ExpressRoute-kretsar. Vi rekommenderar även minst två aktiva/aktiva Internetkretsar eftersom många Office 365-tjänster endast är tillgängliga via Internet.
  
Inuti nätverkets utgående punkt finns många andra enheter och kretsar som spelar en viktig roll för hur människor uppfattar tillgänglighet. De här delarna av dina anslutningsscenarier omfattas inte av ExpressRoute- eller Office 365-tjänstenivåavtalen, men de spelar en viktig roll i slutet av tjänstens tillgänglighet så som den uppfattas av personer i organisationen.
  
Fokusera på de personer som använder och använder Office 365. Om ett fel i någon komponent skulle påverka upplevelsen av att använda tjänsten letar du efter sätt att begränsa den totala procentandelen personer som påverkas. Om ett redundansläge är driftsläget komplext kan du överväga att ta hänsyn till personernas upplevelse av en lång tid för återställning och leta efter driftsmässiga, enkla och automatiserade redundanslägen.
  
Utanför ditt nätverk har Office 365, ExpressRoute och din ExpressRoute-leverantör tillgång i olika nivåer av tillgänglighet.
  
### <a name="service-availability"></a>Tjänstetillgänglighet
  
- Office 365-tjänster omfattas av väldefinierade serviceavtal [,](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)som omfattar statistik för drifttid och tillgänglighet för enskilda tjänster. En orsak till att Office 365 kan bibehålla så höga tjänstetillgänglighetsnivåer är möjligheten för enskilda komponenter att smidigt växla mellan de många Microsoft-datacenter med hjälp av det globala Microsoft-nätverket. Den här redundansen sträcker sig från datacentret och nätverket till flera egresspunkter för Internet och möjliggör smidig redundans för de som använder tjänsten.

- ExpressRoute [tillhandahåller ett tillgänglighets-SLA på 99,9 %](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) på enskilda dedikerade kretsar mellan Microsoft Network Edge och ExpressRoute-leverantören eller partnerinfrastrukturen. De här tjänstenivåerna tillämpas på ExpressRoute-kretsnivån, som består av två oberoende sammankopplingar mellan redundant Microsoft-utrustning och [nätverksleverantörens](/azure/expressroute/expressroute-introduction) utrustning på varje peeringplats.

### <a name="provider-availability"></a>Leverantörstillgänglighet
  
- Microsofts servicenivåavtal slutar hos din ExpressRoute-leverantör eller partner. Det här är också den första plats där du kan göra val som påverkar din tillgänglighetsnivå. Du bör noggrant utvärdera de egenskaper för arkitektur, tillgänglighet och motståndskraft som expressRoute-leverantören erbjuder mellan din nätverks perimeter och leverantörens anslutning på varje Microsoft-peeringplats. Var uppmärksam på både de logiska och fysiska aspekterna av redundans, peeringutrustning, wan-kretsar från operatören och alla ytterligare värde för att lägga till tjänster, till exempel NAT-tjänster eller hanterade brandväggar.

### <a name="designing-your-availability-plan"></a>Utforma tillgänglighetsplanen
  
Vi rekommenderar att du planerar och utformar hög tillgänglighet och motståndskraft i dina end-to-end-anslutningsscenarier för Office 365. En utformning ska inkludera:
  
- Inga enskilda felpunkter, inklusive både Internet- och ExpressRoute-kretsar.

- En minimering av antalet personer som påverkas och varaktigheten av inverkan för de mest förväntade fellägena.

- En optimering för enkel, upprepningsbar och automatisk återställningsprocess från de mest förväntade fellägena.

- Stöd för nätverkstrafikens och funktionernas fullständiga behov genom redundanta linjer och utan avsevärd försämring.

Dina anslutningsscenarier bör inkludera en nätverkstopologi som är optimerad för flera oberoende och aktiva nätverksrappar till Office 365. Det här ger en bättre end-to-end-tillgänglighet än en topologi som är optimerad för redundans på nivån för enskilda enheter eller utrustning.
  
> [!TIP]
> Om användarna är fördelade över flera världsdelar eller geografiska områden och var och en av dessa platser ansluter över redundanta WAN-kretsar till en enda lokal plats där en enda ExpressRoute-krets finns, kommer användarna att uppleva färre end-to-end-tjänstetillgänglighet än med en nätverkstopologidesign som inkluderar oberoende ExpressRoute-kretsar som ansluter de olika regionerna till närmaste peeringplats.
  
Vi rekommenderar att du etablerar minst två ExpressRoute-kretsar med varje krets som ansluter till med olika geografiska peeringplatser. Du bör tillhandahålla detta aktiva par med kretsar för varje region där personer kommer att använda ExpressRoute-anslutningar för Office 365-tjänster. På så sätt kan varje region förbli ansluten under en katastrof som påverkar en större plats, till exempel ett datacenter eller en peeringplats. Om du konfigurerar dem som aktiva/aktiva kan slutanvändartrafiken distribueras över flera nätverksränder. Det här minskar omfattningen av personer som påverkas vid avbrott i enhet eller nätverksutrustning.
  
Vi rekommenderar inte att du använder en enda ExpressRoute-krets med Internet som säkerhetskopia.
  
### <a name="example-2-failover-and-high-availability"></a>Exempel 2: Redundans och hög tillgänglighet
  
Woodgrove Banks utformning för flera geografiska platser har genomgått en granskning av dirigering, bandbredd och säkerhet och ska nu gå igenom en granskning av hög tillgänglighet. Woodgrove ser på hög tillgänglighet som något som omfattar tre kategorier. motståndskraft, tillförlitlighet och redundans.
  
Med motståndskraft kan Woodgrove återställa efter fel snabbt. Med tillförlitlighet kan Woodgrove erbjuda enhetliga resultat i systemet. Med redundans kan Woodgrove växla mellan en eller flera speglade förekomster av infrastrukturen.
  
Inom varje kantkonfiguration har Woodgrove redundanta brandväggar, proxy och IDS. I Nordamerika har Woodgrove en kantkonfiguration i sitt datacenter i Dallas och en annan kantkonfiguration i sitt datacenter i Virginia. Den redundanta utrustningen på varje plats ger den platsen motståndskraft.
  
Nätverkskonfigurationen på Woodgrove Bank är baserad på några viktiga principer:
  
- Det finns flera Azure ExpressRoute-kretsar inom varje geografisk region.

- Varje krets inom en region har stöd för all nätverkstrafik inom den regionen.

- Dirigeringen kommer tydligt att föredra den ena eller den andra sökvägen beroende på tillgänglighet, plats och så vidare.

- Växlingen mellan Azure ExpressRoute-kretsar sker automatiskt utan ytterligare konfiguration eller åtgärd från Woodgroves del.

- Växlingen mellan internetkretsar sker automatiskt utan ytterligare konfiguration eller åtgärd från Woodgrove.

I den här konfigurationen med redundans på den fysiska och virtuella nivån kan Woodgrove Bank erbjuda lokal, regional och global motståndskraft på ett tillförlitligt sätt. Woodgrove valde den här konfigurationen efter att ha utvärderat en enda Azure ExpressRoute-krets per region samt möjligheten med fel till internet.
  
Om Woodgrove inte hade kunnat ha flera Azure ExpressRoute-kretsar per region hade dirigeringen av trafik med ursprung i Nordamerika till Azure ExpressRoute-kretsen i Asienhavsområdet en godtagbar nivå av fördröjningar, och den nödvändiga DNS-vidarebefordringskonfigurationen hade lagt till komplexitet.
  
Vi rekommenderar inte att du använder Internet som en alternativ konfiguration. Det bryter mot Woodgroves tillförlitlighetsprincip och resulterar i en inkonsekvent upplevelse när anslutningen används. Manuell konfiguration skulle dessutom behöva redundans med hänsyn till de BGP-annonseringar som har konfigurerats, NAT-konfigurationen, DNS-konfigurationen och proxykonfigurationen. Denna extra redundanskomplexitet ökar tiden för återställning och minskar deras möjlighet att diagnostisera och felsöka stegen som ingår.
  
Har du fortfarande frågor om hur du planerar för och implementerar trafikhantering eller Azure ExpressRoute? Läs även vår nätverks- [och prestandavägledning eller](./network-planning-and-performance.md) Vanliga frågor och [svar om Azure ExpressRoute.](/azure/expressroute/expressroute-faqs)
  
## <a name="working-with-azure-expressroute-providers"></a>Arbeta med Azure ExpressRoute-leverantörer
<a name="BKMK_high-availability"> </a>

Välj platser för kretsarna baserat på din bandbredd, svarstid, säkerhet och planering för hög tillgänglighet. När du känner till de optimala platserna bör du granska den aktuella [listan över leverantörer per region.](/azure/expressroute/expressroute-locations)
  
Samarbeta med din leverantör eller dina leverantörer för att välja de bästa anslutningsalternativen, punkt till punkt, flera punkt eller värdbaserade. Kom ihåg att du kan kombinera och matcha anslutningsalternativen så länge bandbredden och andra redundanta komponenter stöder din planering för dirigering och hög tillgänglighet.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Relaterade ämnen
<a name="BKMK_high-availability"> </a>

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365-anslutningar](managing-expressroute-for-connectivity.md)
  
[Dirigering med ExpressRoute för Office 365](routing-with-expressroute.md)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Använda BGP-communities i ExpressRoute för Office 365-scenarier](bgp-communities-in-expressroute.md)
  
[Prestanda för mediekvalitet och nätverksanslutning i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimera ditt nätverk för Skype för företag – Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute och QoS i Skype för företag – Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtalsflöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 nätverks- och prestandajustering](network-planning-and-performance.md)
  
[Office 365-slutpunkter – vanliga frågor och svar](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)