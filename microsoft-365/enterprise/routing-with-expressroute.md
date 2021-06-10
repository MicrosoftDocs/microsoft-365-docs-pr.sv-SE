---
title: Dirigering med ExpressRoute för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: I den här artikeln kan du läsa mer om Azure ExpressRoute-dirigeringskrav, kretsar och dirigeringsdomäner för användning Office 365.
ms.openlocfilehash: b455ed7e53b3018babb1abd58919a077fb9d0685
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687175"
---
# <a name="routing-with-expressroute-for-office-365"></a>Dirigering med ExpressRoute för Office 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För ordentlig förståelse av att dirigera trafik till Office 365 med Azure ExpressRoute [](/azure/expressroute/expressroute-routing) måste du en ha ett bra grepp om de huvudsakliga ExpressRoute-dirigeringskraven och ExpressRoute-kretsarna och [dirigeringsdomänerna.](/azure/expressroute/expressroute-circuit-peerings) De här lägger de grunder för användning av ExpressRoute som Office 365 kunderna förlitar sig på.
  
Här är några av de viktigaste punkterna i ovanstående artiklar som du måste förstå:
  
- ExpressRoute-kretsar är inte mappade till specifik fysisk infrastruktur, men är en logisk anslutning som upprättas på en enda peeringplats av Microsoft och en peeringleverantör för din räkning.

- Det finns en 1:1-mappning mellan en ExpressRoute-krets och en kunds s-nyckel.

- Varje krets har stöd för två oberoende peeringrelationer (Azure Private-peering och Microsoft-peering). Office 365 microsoft-peering krävs.

- Varje krets har en fast bandbredd som delas mellan alla peeringrelationer.

- Alla offentliga IPv4-adresser och offentliga AS-nummer som ska användas för ExpressRoute-kretsen måste valideras som ägda av dig eller tilldelas exklusivt av ägaren av adressintervallet.

- De virtuella ExpressRoute-kretsarna är redundanta globalt och följer de BGP-dirigeringsrutiner som är standard. Därför rekommenderar vi två fysiska kretsar per utgång till din leverantör i en aktiv/aktiv konfiguration.

Mer information [om vilka](/azure/expressroute/expressroute-faqs) tjänster som stöds, kostnader och konfigurationsinformation finns på sidan Vanliga frågor och svar. I [ExpressRoute-platsartikeln finns](/azure/expressroute/expressroute-locations) information om listan över anslutningsleverantörer som erbjuder Microsoft-peeringstöd. Vi har även spelat in en 10-delar lång [Azure ExpressRoute](https://channel9.msdn.com/series/aer) för Office 365 på Kanal 9 för att bättre förklara begreppen.
  
## <a name="ensuring-route-symmetry"></a>Säkerställa ruttsymmetri

The Office 365 frontend servers are accessible on both the Internet and ExpressRoute. Servrarna föredrar att dirigeras tillbaka lokalt via ExpressRoute-kretsar när båda är tillgängliga. Det kan därför finnas en möjlighet till asymmetri om trafiken från nätverket föredrar att dirigeras över dina internetkretsar. Asymmetriska rutter är ett problem eftersom enheter som utför tillståndsfull paketinspektion kan blockera returtrafik som följer en annan väg än den som de utgående paketen följde.
  
Oavsett om du initierar en anslutning Office 365 via Internet eller ExpressRoute måste källan vara en offentligt dirigerbar adress. När många kunder använder peering direkt med Microsoft är det inte praktiskt möjligt att ha privata adresser där duplicering är möjlig mellan kunder.
  
Följande är scenarier där kommunikation från Office 365 till ditt lokala nätverk kommer att initieras. För att förenkla din nätverksdesign rekommenderar vi att du dirigerar dem via Internet-sökvägen.
  
- SMTP-tjänster som e-post från en Exchange Online-klientorganisation till en lokal värd eller SharePoint Online-e-post som skickas från SharePoint Online till en lokal värd. SMTP-protokollet används mer brett i Microsofts nätverk än de routningsprefix som delas över ExpressRoute-kretsar och reklam på lokala SMTP-servrar över ExpressRoute orsakar fel med dessa andra tjänster.

- ADFS under verifiering av lösenord för att logga in.

- [Exchange Server för hybriddistributioner](/exchange/exchange-hybrid).

- [SharePoint federerad hybridsökning](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint BCS-hybrid](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype för företag hybrid](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) och/eller [Skype för företag federation](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype för företag Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

För att Microsoft ska kunna dirigera de här dubbelriktade trafikflödena tillbaka till ditt nätverk måste BGP-rutterna till dina lokala enheter delas med Microsoft. När du annonserar routeprefix till Microsoft via ExpressRoute bör du följa de här metodtipsen:

1) Annonsera inte samma offentliga IP-adressrouteprefix till det offentliga Internet och via ExpressRoute. Vi rekommenderar att annonserna för IP BGP-ruttprefix till Microsoft via ExpressRoute kommer från ett intervall som inte annonseras till internet alls. Om detta inte är möjligt på grund av det tillgängliga IP-adressutrymmet är det viktigt att säkerställa att du annonserar ett mer specifikt intervall via ExpressRoute än några internetkretsar.

2) Använd separata NAT IP-pooler per ExpressRoute-krets och separat mot dessa internetkretsar.

3) Observera att alla vägar som annonseras till Microsoft "attraherar" nätverkstrafik från valfri server i Microsofts nätverk, inte bara de som dirigeras till ditt nätverk via ExpressRoute. Annonsera bara routes till servrar där routningsscenarier definieras och förstås av ditt team. Annonsera separata IP Address-routeprefix vid var och en av flera ExpressRoute-kretsar från ditt nätverk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Fastställa vilka program och funktioner som dirigeras genom ExpressRoute

När du konfigurerar en peeringrelation med hjälp av Microsoft-peeringdirigeringsdomänen och godkänns för rätt åtkomst kommer du att kunna se alla PaaS- och SaaS-tjänster som är tillgängliga via ExpressRoute. De Office 365-tjänster som utformats för ExpressRoute kan hanteras med [BGP-communities](./bgp-communities-in-expressroute.md) eller [routefilter.](/azure/expressroute/how-to-routefilter-portal)
  
Andra program, till Office 365 Video, är ett Office 365 program. Men Office 365 Video består av tre olika komponenter: portalen, direktuppspelningstjänsten och innehållsleveransnätverket. Portalen finns i SharePoint Online, direktuppspelningstjänsten i Azure Media Services och innehållsleveransnätverket finns i Azure CDN. I följande tabell beskrivs dessa komponenter.

|**Komponent**|**Underliggande program**|**Ingår i SharePoint BGP-communityn online?**|**Använd**|
|:-----|:-----|:-----|:-----|
|Office 365 Videoportal  <br/> |SharePoint Online  <br/> |Ja  <br/> |Konfiguration, uppladdning  <br/> |
|Office 365 Tjänst för direktuppspelning av video  <br/> |Azure Media Services  <br/> |Nej  <br/> |Direktuppspelningstjänst som används om videon inte är tillgänglig från CDN  <br/> |
|Office 365 Nätverk för videoinnehållsleverans  <br/> |Azure CDN  <br/> |Nej  <br/> |Primär källa för nedladdning/direktuppspelning av video. [Läs mer om Office 365 videonätverk](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Alla Office 365 som är tillgängliga med Microsoft-peering visas i artikeln om [Office 365-slutpunkter](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) efter programtyp och FQDN. Anledningen till att använda FQDN i tabellerna är att kunderna kan hantera trafik med hjälp av PAC-filer eller andra proxykonfigurationer. Se vår guide för att hantera [Office 365 slutpunkter,](./managing-office-365-endpoints.md) till exempel PAC-filer.
  
I vissa situationer har vi använt en jokerteckendomän där en eller flera under-FQDN annonseras på ett annat sätt än jokerteckendomänen på högre nivå. Det här inträffar vanligtvis när jokertecknet representerar en lång lista med servrar som alla annonseras till ExpressRoute och Internet, medan en liten delmängd av destinationer endast annonseras till Internet, eller tvärtom. I tabellerna nedan kan du se var skillnaderna finns.
  
Den här tabellen visar FQDN med jokertecken som annonseras till både internet och Azure ExpressRoute tillsammans med under-FQDN som endast annonseras till internet.

|**Jokerteckendomän som annonseras till ExpressRoute- och Internetkretsar**|**Endast under-FQDN som annonseras till internetkretsar**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Vanligtvis är PAC-filer tänkta att skicka nätverksbegäran till ExpressRoute-annonserade slutpunkter direkt till kretsen och alla andra nätverksbegäran till din proxyserver. Om du konfigurerar en PAC-fil på så sätt komponerar du PAC-filen i följande ordning:
  
1. Inkludera under-FQDN från kolumn två i tabellen ovan högst upp i PAC-filen, som skickar trafiken till din proxyserver. Vi har skapat ett exempel på en PAC-fil som du kan använda i vår artikel om hantering [Office 365 slutpunkter.](./managing-office-365-endpoints.md)

2. Inkludera alla FQDN som är [](./urls-and-ip-address-ranges.md) markerade som annonserade till ExpressRoute i den här artikeln under det första avsnittet och skicka trafiken direkt till ExpressRoute-kretsen.

3. Inkludera övriga nätverksslutpunkter eller regler under de här två posterna och skicka trafiken till din proxyserver.

Den här tabellen visar de jokerteckendomäner som annonseras till internetkretsar endast tillsammans med under-FQDN som annonseras till Azure ExpressRoute- och Internetkretsar. För PAC-filen ovan anges FQDN i kolumn 2 i nedanstående tabell som annonserade till ExpressRoute i länken som det refereras till, vilket innebär att de kommer att inkluderas i den andra gruppen av poster i filen.

|**Domän med jokertecken som endast annonseras till internetkretsar**|**Under-FQDN som annonseras till ExpressRoute- och Internetkretsar**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Dirigering Office 365 trafik via Internet och ExpressRoute

För att du Office 365 det program du väljer måste du fastställa ett antal nyckelfaktorer.
  
1. Hur mycket bandbredd kommer programmet att kräva? Sampling av befintlig användning är den enda tillförlitliga metoden för att fastställa detta i din organisation.

2. Från vilken eller vilka egressplatser vill du att nätverkstrafiken ska lämna ditt nätverk. Du bör planerar att minimera nätverksfördröjning för anslutning till Office 365 eftersom det påverkar prestanda. Eftersom Skype för företag använder röst och video i realtid är det särskilt känslig för stora nätverksfördröjning.

3. Om du vill att alla eller en delmängd av dina nätverksplatser ska använda ExpressRoute.

4. Från vilka platser erbjuder din nätverksleverantör ExpressRoute?

När du har fått svar på de här frågorna kan du tillhandahålla en ExpressRoute-krets som uppfyller behoven av bandbredd och plats. Mer hjälp för nätverksplanering finns i artikeln [Office 365 nätverksjusteringsguide](./network-planning-and-performance.md) och fallstudien om [hur Microsoft hanterar nätverksprestandaplanering.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Exempel 1: En enda geografisk plats
  
Det här exemplet är ett scenario för det fiktiva företaget Trey Research, som har en enda geografisk plats.
  
Anställda på Trey Research får endast ansluta till internettjänster och webbplatser som uttryckligen är tillåtna av säkerhetsavdelningen och via de utgående proxytjänster som är bundna till företagsnätverket och Internetleverantören.
  
Trey Research planerar att använda Azure ExpressRoute för Office 365 och är medvetna om att viss trafik, till exempel trafik med destination för innehållsleveransnätverk, inte kommer att kunna dirigeras via ExpressRoute för Office 365-anslutning. Eftersom all trafik redan som standard dirigeras till proxyenheterna fortsätter dessa förfrågningar att fungera som tidigare. När Trey Research anser att de uppfyller Azure ExpressRoute-dirigeringskraven fortsätter de med att skapa en krets, konfigurera dirigering och länka den nya ExpressRoute-kretsen till ett virtuellt nätverk. När den grundläggande Azure ExpressRoute-konfigurationen är på plats använder Trey Research [#2 PAC-filen](./managing-office-365-endpoints.md) vi publicerar för att dirigera trafik med kundspecifika data via direkta ExpressRoute för Office 365 anslutningar.
  
Som du ser i följande diagram kan Trey Research tillgodose kravet på att dirigera Office 365-trafik via internet och en delmängd av trafiken genom ExpressRoute med hjälp av en kombination av ändringar av dirigerings- och utgående proxy.
  
1. Med hjälp [#2 PAC-fil som vi](./managing-office-365-endpoints.md) publicerar för att dirigera trafik via en separat utgående internetpunkt för Azure ExpressRoute för Office 365.

2. Klienter är konfigurerade med en standardväg till Trey Researchs proxy.

I det här exempelscenariot använder Trey Research en utgående proxyenhet. Kunder som inte använder Azure ExpressRoute för Office 365 kan på samma sätt använda den här tekniken för att dirigera trafik baserat på inspektionskostnaden för trafik till välkända slutpunkter med hög trafik.
  
Följande är de FQDN med Exchange Online, SharePoint Online Skype för företag online:
  
![Gränsnätverk för ExpressRoute-kunder](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com tillsammans med IP-intervallen för icke-TCP-trafik

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Läs mer om [att distribuera och hantera proxyinställningar i Windows 8](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) och se Office 365 att din proxy inte [begränsas.](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)
  
Trey Research har ingen hög tillgänglighet med en enda ExpressRoute-krets. I händelse av att Treys redundanta par av kantenheterna för ExpressRoute-anslutningen fallerar finns det ingen ytterligare ExpressRoute-krets att växla över till. Det här gör att Trey Research blir ett problem eftersom manuell omkonfiguration och i vissa fall nya IP-adresser krävs för att det ska gå att gå över till Internet. Om Trey vill ha hög tillgänglighet är den enklaste lösningen att lägga till ytterligare ExpressRoute-kretsar för varje plats och konfigurera kretsarna på ett aktivt/aktivt sätt.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Dirigering av ExpressRoute för Office 365 med flera platser

Det sista scenariot, dirigering Office 365 trafik genom ExpressRoute, utgör grunden för ännu mer komplicerad dirigeringsarkitektur. Oavsett antal platser, antal världsdelar där dessa platser finns, antal ExpressRoute-kretsar och så vidare kommer det att krävas att kunna dirigera viss trafik till Internet och viss trafik genom ExpressRoute.
  
Ytterligare frågor som måste besvaras för kunder med flera platser i flera geografiska områden omfattar:
  
1. Behöver du en ExpressRoute-krets på varje plats? Om du använder Skype för företag Online eller är bekymrad över känsligheten för fördröjningar i SharePoint Online eller Exchange Online rekommenderas ett redundant par aktiva/aktiva ExpressRoute-kretsar på varje plats. Mer information Skype för företag om mediekvaliteten och nätverksanslutningsguiden.

2. Om en ExpressRoute-krets inte är tillgänglig i en viss region, hur Office 365 trafik till destinationen dirigeras?

3. Vilken är den rekommenderade metoden för att konsolidera trafik när det gäller nätverk med många små platser?

Var och en av dessa presenterar en unik utmaning som kräver att du utvärderar ditt eget nätverk och de alternativ som är tillgängliga från Microsoft.

|**Att tänka på**|**Nätverkskomponenter att utvärdera**|
|:-----|:-----|
|Kretsar på mer än en plats  <br/> |Vi rekommenderar minst två kretsar konfigurerade på aktivt/aktivt sätt.  <br/> Behov av kostnad, svarstid och bandbredd måste jämföras.  <br/> Använd BGP-dirigeringskostnad, PAC-filer och NAT för att hantera dirigering med flera kretsar.  <br/> |
|Dirigering från platser utan en ExpressRoute-krets  <br/> |Vi rekommenderar en utgång och DNS-upplösning så nära den person som initierar begäran Office 365.  <br/> DNS-vidarebefordran kan användas för att låta fjärranslutna kontor identifiera rätt slutpunkt.  <br/> Klienter i fjärranslutna kontor måste ha en route tillgänglig som ger åtkomst till ExpressRoute-kretsen.  <br/> |
|Konsolidering av små kontor  <br/> |Tillgänglig bandbredd och dataanvändning ska jämföras noggrant.  <br/> |

> [!NOTE]
> Microsoft föredrar ExpressRoute via internet om routen är tillgänglig oavsett fysisk plats.
  
Var och en av dessa överväganden måste beaktas för varje unikt nätverk. Nedan följer ett exempel.
  
### <a name="example-2-multi-geographic-locations"></a>Exempel 2: Flera geografiska platser
  
Det här exemplet är ett scenario för det fiktiva företaget Humongous Insurance. Företaget har flera geografiska platser.
  
Humongous Insurance är geografiskt utspridda med kontor över hela världen. De vill implementera Azure ExpressRoute för Office 365 ha kvar sin Office 365 trafik via direkta nätverksanslutningar. Humongous Insurance har också kontor på ytterligare två världsdelar. Anställda på det fjärranslutna kontor där ExpressRoute inte är möjligt måste dirigeras tillbaka till ett eller båda de primära anläggningar för att använda en ExpressRoute-anslutning.
  
Den vägledande principen är att få trafik Office 365 på väg till ett Microsoft-datacenter så snabbt som möjligt. I det här exemplet måste Humongous Insurance bestämma om deras fjärranslutna kontor ska dirigeras via Internet till ett Microsoft-datacenter via vilken anslutning som helst så snabbt som möjligt eller om deras fjärranslutna kontor ska dirigeras via ett internt nätverk för att komma till ett Microsoft-datacenter via en ExpressRoute-anslutning så snabbt som möjligt.
  
Microsofts datacenter, nätverk och programarkitektur är utformad för att dra stora hänsyn till globalt skilda kommunikationer och ge dem bästa möjliga service. Det här är ett av de största nätverken i världen. Begäranden som är Office 365 som blir kvar i kundens nätverk längre än nödvändigt kommer inte att kunna dra nytta av den här arkitekturen.
  
I Humongous Insurances situation bör de fortsätta beroende på vilka program de tänker använda via ExpressRoute. Om de till exempel är en Skype för företag Online-kund eller planerar att använda ExpressRoute-anslutning när de ansluter till externa Skype för företag Online-möten rekommenderar guiden för Skype för företag Online-mediakvalitet och nätverksanslutning att de etablerar en ytterligare ExpressRoute-krets för den tredje platsen. Det kan vara dyrare ur ett nätverksperspektiv. Dock kan dirigeringsförfrågningar från en världsdel till en annan innan de levereras till ett Microsoft-datacenter ge en dålig eller oanvändbar upplevelse under Skype för företag onlinemöten och kommunikation.
  
Om Humongous Insurance inte använder eller inte planerar att använda Skype för företag Online på något sätt kan dirigering av nätverkstrafik på väg till Office 365 tillbaka till en världsdel med en ExpressRoute-anslutning vara möjlig, men kan orsaka onödig fördröjning eller TCP-överbelastning. I båda fallen rekommenderas dirigering av trafik på väg till Internet till Internet på den lokala platsen för att dra nytta av de innehållsleveransnätverk som Office 365 förlitar sig på.
  
![Multigeografi för ExpressRoute](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
När Humongous Insurance planerar sin strategi för flera geografiska platser finns det ett antal saker att tänka på kring kretsstorlek, antal kretsar, redundans osv.
  
Med ExpressRoute på en enda plats med flera regioner som försöker använda kretsen vill Humongous Insurance säkerställa att anslutningar till Office 365 från det fjärranslutna kontoret skickas till det Office 365-datacenter som ligger närmast huvudkontoret och tas emot vid huvudkontoret. Humongous Insurance har implementerat en DNS-vidarebefordran som minskar det antal resor och DNS-uppslag som krävs för att upprätta lämplig anslutning till den Office 365-miljö som ligger närmast huvudkontorets utgående internetpunkt. Det förhindrar klienten från att lösa en lokal klientserver och säkerställer att den Front-End-server som personen ansluter till finns nära huvudkontoret där Humongous Insurance peering med Microsoft. Du kan också lära dig [att tilldela en villkorsstyrd vidarebefordrare för ett domännamn.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))
  
I det här scenariot löser trafik från det fjärranslutna kontoret Office 365-frontendinfrastrukturen i Nordamerika och använder Office 365 för att ansluta till backendservrarna enligt arkitekturen för Office 365-programmet. Till exempel Exchange Online skulle avsluta anslutningen i Nordamerika och frontendservrarna skulle ansluta till e-postbackendservern där klientorganisationen finns. Alla tjänster har en allmänt distribuerad front door-tjänst bestående av en encast- och anycast-destinationer.
  
Om Humongous har större kontor på flera världsdelar rekommenderas minst två aktiva/aktiva kretsar per region för att minska svarstiden för känsliga program som Skype för företag Online. Om alla kontor finns i en enda världsdel, eller inte använder samarbete i realtid, är en konsoliderad eller distribuerad utgående punkt ett kundspecifikt beslut. När det finns flera kretsar tillgängliga säkerställer BGP-routningen redundans om ingen enskild krets blir tillgänglig.
  
Läs mer om [exempelkonfigurationer för dirigering](/azure/expressroute/expressroute-config-samples-routing) och [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) .
  
## <a name="selective-routing-with-expressroute"></a>Selektiv dirigering med ExpressRoute

Selektiv dirigering med ExpressRoute kan behövas av en rad olika anledningar, till exempel testning eller distribution av ExpressRoute till en delmängd av användarna. Det finns olika verktyg kunderna kan använda för att selektivt dirigera Office 365 nätverkstrafik genom ExpressRoute:
  
1. **Filtrering/separering** vid dirigering – tillåta BGP-rutter att Office 365 över ExpressRoute för en delmängd av dina undernät eller routrar. Med det här dirigeras rutter selektivt efter kundnätverkssegment eller fysisk kontorsplats. Det här är vanligt vid spridd utrullning av ExpressRoute för Office 365 och är konfigurerat på dina BGP-enheter.

2. **PAC-filer/URL:er** – dirigerar Office 365 nätverkstrafik på väg till specifika FQDN för att dirigera den på en viss rutt. Det här dirigerar selektivt efter de klientdatorer som identifieras med [PAC-fildistributionen.](./managing-office-365-endpoints.md)

3. **Routefiltrering**  -  [Routefilter](/azure/expressroute/how-to-routefilter-portal) är ett sätt att använda en delmängd av de tjänster som stöds via Microsoft-peering.

4. **BGP-communities** – filtrerar baserat på [BGP-communitytaggar](./bgp-communities-in-expressroute.md) som gör att en kund kan avgöra vilka Office 365-program som ska passera genom ExpressRoute och vilka som ska gå via Internet.

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>Relaterade ämnen

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365 anslutning](managing-expressroute-for-connectivity.md)
  
[Nätverksplanering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Prestanda för mediekvalitet och nätverksanslutning i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimera ditt nätverk för Skype för företag – Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute och QoS i Skype för företag Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtalsflöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Använda BGP-communities i ExpressRoute för Office 365 scenarier](bgp-communities-in-expressroute.md)
  
[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).
  
[Office 365-webbadresser och IP-adressintervall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 nätverks- och prestandajustering](network-planning-and-performance.md)
