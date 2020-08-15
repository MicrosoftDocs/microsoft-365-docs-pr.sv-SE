---
title: Routning med ExpressRoute för Office 365
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
description: I den här artikeln lär du dig mer om Azure ExpressRoute-routningsfunktioner, kretsar och routningsdomäner för användning med Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694380"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routning med ExpressRoute för Office 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

För att du ska kunna förstå flödes trafiken korrekt i Office 365 med Azure ExpressRoute behöver du en fast förstå av de grundläggande [ExpressRoute-Dirigerings kraven](https://azure.microsoft.com/documentation/articles/expressroute-routing/) och de [ExpressRoute kretsar och routningsdomäner](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/). Dessa utformar de grundläggande funktionerna för att använda ExpressRoute som Office 365-kunder kommer att lita på.
  
Några av de viktigaste objekten i de ovanstående artiklarna som du behöver förstå inkluderar:
  
- ExpressRoute kretsar är inte mappade till specifik fysisk infrastruktur, men är en logisk anslutning till en enda peering-plats av Microsoft och en peering-leverantör åt dig.

- Det finns en 1:1-mappning mellan en ExpressRoute-krets och en kund s---.

- Varje krets har stöd för två oberoende peering-relationer (Azure Private peering och Microsoft peering); Office 365 kräver Microsoft peering.

- Varje krets har en fast bandbredd som delas mellan alla peering-relationer.

- Alla offentliga IPv4-adresser och offentliga AS-nummer som används för ExpressRoute-kretsen måste val IDE ras som ägs av dig, eller tilldelas exklusivt till dig av ägaren till adress området.

- De virtuella ExpressRoute kretsarna är överflödiga globalt och följer standard rutiner för BGP-routning. Därför rekommenderar vi två fysiska kretsar per utgång till din leverantör i en aktiv/aktiv konfiguration.

Se [sidan med vanliga frågor](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) för mer information om tjänster, kostnader och konfigurations uppgifter. Se [artikeln ExpressRoute locations](https://azure.microsoft.com/documentation/articles/expressroute-locations/) för information om listan med anslutnings leverantörer som erbjuder Microsofts peering-support. Vi har också spelat in en 10-parts [Azure ExpressRoute for Office 365-utbildnings](https://channel9.msdn.com/series/aer) serie på kanal 9 för att hjälpa dig att förklara begreppen mer noggrant.
  
## <a name="ensuring-route-symmetry"></a>Säkerställer flödes symmetri

Front servrarna för Office 365 är tillgängliga på både Internet och ExpressRoute. Dessa servrar föredrar att omdirigeras till lokala via ExpressRoute kretsar när båda är tillgängliga. På grund av det finns det en möjlighet att cirkulera asymmetri kring om trafik från nätverket föredrar att dirigera över dina Internet kretsar. Asymmetriska vägar är ett problem eftersom enheter som utför tillstånds känslig paket kontroll kan blockera retur trafik som följer en annan sökväg än de utgående paketen.
  
Oavsett om du startar en anslutning till Office 365 via Internet eller ExpressRoute, måste källan vara en offentligt dirigerad adress. Med många kunder är det inte möjligt att vara med privata adresser direkt med Microsoft, som är möjliga att dubblera mellan kunder.
  
Följande är scenarier där kommunikation från Office 365 till ditt lokala nätverk initieras. För att förenkla nätverks utformningen rekommenderar vi att du dirigerar över Internet-sökvägen.
  
- SMTP-tjänster som e-post från en Exchange Online-klient organisation till en lokal värd eller SharePoint Online-e-post som skickas från SharePoint Online till en lokal värd. SMTP-protokollet används på ett mer brett sätt i Microsofts nätverk än för de väg-prefix som delas via ExpressRoute kretsar och annonsering på lokala SMTP-servrar via ExpressRoute kan orsaka problem med dessa andra tjänster.

- ADFS vid lösen ords verifiering för inloggning.

- [Hybrid distributioner av Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- [SharePoint-federerad hybrid sökning](https://technet.microsoft.com/library/dn197174.aspx).

- [SharePoint hybrid BCS](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype för företag – hybrid](https://technet.microsoft.com/library/jj205403.aspx) -och/eller [Skype för företag-Federation](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Moln kopplingen Skype för företag](https://technet.microsoft.com/library/mt605227.aspx ).

För att Microsoft ska kunna växla tillbaka till nätverket för dessa dubbelriktade trafik flöden måste BGP-vägarna till dina lokala enheter delas med Microsoft. När du annonserar väg-prefix till Microsoft over ExpressRoute ska du följa de här rekommendationerna:

1) Annonsera inte samma allmänna IP-adressprefix för det offentliga Internet och över ExpressRoute. Vi rekommenderar starkt att annonsering av IP BGP-routing till Microsoft via ExpressRoute från ett område som inte annonseras till Internet alls. Om det inte går att nå på grund av det tillgängliga IP-adressutrymmet är det viktigt att se till att du annonserar ett mer specifikt område över ExpressRoute än alla Internet kretsar.

2) Använd separata IP-pooler för NAT per ExpressRoute-krets och skilj till det för dina Internet kretsar.

3) Observera att alla vägar som annonseras till Microsoft kan lura nätverks trafik från vilken server som helst i Microsofts nätverk, inte bara för de som pratar med ExpressRoute. Annonsera bara vägar till servrar där routningsfunktioner är definierade och väl förstås av din grupp. Annonsera olika prefix för IP-ExpressRoute på var och en av de olika vägarna i ditt nätverk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Bestämma vilka program och funktioner som ska vidarebefordras via ExpressRoute

När du konfigurerar en peering-relation med Microsoft peering routing-domänen och är godkänd för lämplig åtkomst kan du se alla PaaS-och SaaS-tjänster som är tillgängliga via ExpressRoute. Office 365-tjänsterna som är avsedda för ExpressRoute kan hanteras med [BGP-communities](https://aka.ms/bgpexpressroute365) eller [väg filter](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal).
  
Andra program, till exempel Office 365-Video, är ett Office 365-program. Office 365-Video ingår i tre olika komponenter, portalen, streaming-tjänsten och innehålls leverans nätverket. Portalen bor i SharePoint Online, streaming-tjänsten bor i Azure Media Services och innehålls leverans nätverket i Azure CDN. Följande tabell beskriver dessa komponenter.

|**Komponent**|**Underliggande program**|**Ingår i SharePoint Online BGP community?**|**Använd**|
|:-----|:-----|:-----|:-----|
|Office 365 Video-Portal  <br/> |SharePoint Online  <br/> |Ja  <br/> |Konfiguration, ladda upp  <br/> |
|Office 365 video streaming service  <br/> |Azure Media Services  <br/> |Nej  <br/> |Direkt uppspelnings tjänst som används i händelse av att videon inte är tillgänglig från CDN  <br/> |
|Office 365-leverans nätverk för innehålls innehåll  <br/> |Azure CDN  <br/> |Nej  <br/> |Primär källa för nedladdning/uppspelning av video. [Läs mer om Office 365-videosamtal](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Var och en av de Office 365-funktioner som är tillgängliga med Microsoft peering visas i [artikeln om slut punkter för office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) efter program typ och FQDN. Skälet till att använda FQDN i tabellerna är att tillåta att kunder hanterar trafik med PAC-filer eller andra konfigurationsfiler, se vår guide för att [Hantera Office 365-slutpunkter](https://aka.ms/manageo365endpoints) för till exempel PAC-filer.
  
I vissa situationer har vi använt en domän med jokertecken där en eller flera underdomän-FQDN annonseras annorlunda än domänen med högre nivå. Det här inträffar vanligt vis när jokertecken representerar en lång lista med servrar som alla annonseras till ExpressRoute och Internet, medan en liten under uppsättning destinationer annonseras bara till Internet, eller tvärtom. Se tabellerna nedan för att förstå var skillnaderna är.
  
I den här tabellen visas FQDN-namn för jokertecken som annonseras för både Internet och Azure ExpressRoute bredvid de underdomän-FQDN som endast annonseras för Internet.

|**Domän med jokertecken som annonseras till ExpressRoute och Internet kretsar**|**Underordnad FQDN annonseras endast för Internet kretsar**|
|:-----|:-----|
|\*. microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*. officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Vanligt vis är PAC-filer avsedda att skicka nätverks förfrågningar till ExpressRoute annonserade slut punkter direkt till kretsen och alla andra nätverks förfrågningar till din proxyserver. Om du konfigurerar en PAC-fil skriver du in PAC-filen i följande ordning:
  
1. Inkludera underdomän-FQDN från kolumn två i tabellen ovan längst upp i PAC-filen, och skicka trafiken till din proxyserver. Vi har byggt en exempel-fil som du kan använda i den här artikeln om hur du [hanterar Office 365-slutpunkter](https://aka.ms/manageexpressroute365).

2. Ta med alla FQDN: er som är markerade som annonserade för ExpressRoute i [den här artikeln](https://aka.ms/o365endpoints) under det första avsnittet, och skickar trafiken direkt till ExpressRoute-kretsen.

3. Inkludera eventuella andra nätverks slut punkter eller regler under de här två posterna, vilket skickar trafiken till din proxyserver.

I den här tabellen visas de jokertecken som endast annonseras för Internet kretsar bredvid de underordnade FQDN: er som annonseras för Azure ExpressRoute och Internet kretsar. För din PAC-fil ovan anges FQDN-namn i kolumn två i tabellen nedan under annonsering till ExpressRoute i länken som refereras, vilket innebär att de tas med i den andra gruppen med poster i filen.

|**Domän med jokertecken som endast annonseras för Internet kretsar**|**Underordnad FQDN annonseras till ExpressRoute och Internet kretsar**|
|:-----|:-----|
|\*. office.com  <br/> |\*. outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*. office.net  <br/> |agent.office.net  <br/> |
|\*. office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*. outlook.com  <br/> |\*. protection.outlook.com  <br/> \*. mail.protection.outlook.com  <br/> Autodiscover- \<tenant\> . Outlook.com  <br/> |
|\*. windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Dirigera Office 365-trafik via Internet och ExpressRoute

För att dirigera till Office 365-programmet som du väljer måste du fastställa ett antal viktiga faktorer.
  
1. Hur mycket bandbredd som behövs för programmet. Att använda befintlig användning är den enda säkra metoden för att fastställa detta i din organisation.

2. Vilka slutplats (er) som nätverks trafiken ska lämna nätverket ifrån. Du bör planera för att minimera nätverks fördröjningen för anslutning till Office 365 eftersom detta påverkar prestanda. Eftersom Skype för företag använder röst och video i real tid är det särskilt känsligt för dåligt nätverks svars tid.

3. Om du vill att alla eller en del av nätverks platserna ska använda ExpressRoute.

4. Vilka platser din valda nätverksprovider erbjuder ExpressRoute från.

När du har fastställt svaren på dessa frågor kan du tillhandahålla en ExpressRoute-krets som uppfyller behoven hos bandbredd och plats. Om du vill ha mer hjälp med nätverks planering läser du [nätverks justerings guiden för Office 365](https://aka.ms/tune) och [fallstudien om hur Microsoft hanterar nätverks prestanda planering](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Exempel 1: en enda geografisk plats
  
Det här exemplet är ett scenario för ett fiktivt företag som heter Trey Research och som har en enda geografisk plats.
  
Anställda på Trey Research är bara tillåtna för att ansluta till tjänsterna och webbplatserna på Internet som säkerhets avdelningen uttryckligen tillåter på par av utgående proxyservrar som är placerade mellan företags nätverket och deras Internet leverantör.
  
De Trey Research-planerna för att använda Azure ExpressRoute för Office 365 och en del trafik som trafik till för innehålls leverans nät inte kan dirigera via ExpressRoute för Office 365-anslutningen. Eftersom all trafik redan är inställd på proxyservrar som standard fortsätter dessa förfrågningar att fungera som tidigare. Efter en Trey Research bestämmer de att de kan uppfylla Azure ExpressRoute-routningsfunktioner, de fortsätter med att skapa en krets, konfigurera routning och länka den nya ExpressRoute-kretsen till ett virtuellt nätverk. När den grundläggande Azure ExpressRoute-konfigurationen är på plats använder Trey Research den [#2 PAC-filen som vi publicerar](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) för att dirigera trafik med kundspecifika data via direkt ExpressRoute för Office 365-anslutningar.
  
Som du ser i följande diagram kan Trey Research uppfylla kraven för att dirigera Office 365-trafik över Internet och en delmängd trafik över ExpressRoute med en kombination av ändringar för Routning och utgående proxy-konfiguration.
  
1. Använda [#2 PAC-filen som vi publicerar](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) för att dirigera trafik via en separat Internet träff punkt för Azure ExpressRoute för Office 365.

2. Klienter är konfigurerade med en standard väg mot Trey Researchs proxyservrar.

I det här exemplet använder Trey Research en utgående proxyserver. På samma sätt kan kunder som inte använder Azure ExpressRoute för Office 365 vilja använda den här tekniken för att dirigera trafik utifrån kostnaden för att kontrol lera trafik till välbekanta hög volym slut punkter.
  
De högsta volym-FQDN för Exchange Online, SharePoint Online och Skype för företag – Online är följande:
  
![ExpressRoute kund kant nätverk](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>. SharePoint.com, \<tenant-name\> -My.SharePoint.com, \<tenant-name\> - \<app\> . SharePoint.com

- \*. Lync.com tillsammans med IP-intervall för icke-TCP-trafik

- \*broadcast.officeapps.live.com, \* Excel.officeapps.live.com, \* onenote.officeapps.live.com, \* PowerPoint.officeapps.live.com, \* view.officeapps.live.com, \* Visio.officeapps.live.com, \* Word-Edit.officeapps.live.com, \* Word-View.officeapps.live.com, Office.live.com

Läs mer om hur du [distribuerar och hanterar proxyinställningar i Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) och [kontrol lera att Office 365 inte är begränsat till din proxyserver](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Med en enda ExpressRoute-krets är det ingen hög tillgänglighet för Trey Research. I händelse av att det inte går att betjäna den ExpressRoute anslutningen kan du inte gå till den andra ExpressRoute-kretsen. Detta gör att Trey Research i en predicament som inte är på Internet kräver manuell omkonfigurering och i vissa fall nya IP-adresser. Om Trey vill kunna lägga till hög tillgänglighet är den enklaste lösningen att lägga till ytterligare ExpressRoute-kretsar för varje plats och konfigurera kretsarna på ett aktivt/aktivt sätt.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing ExpressRoute för Office 365 med flera platser

Det sista scenariot, routning av Office 365-trafik över ExpressRoute är grunden för ännu mer komplex cirkulation. Oavsett antalet platser, antalet kontinenter där dessa platser finns, antal ExpressRoute-kretsar och så vidare, så att du kan dirigera viss trafik till Internet och viss trafik via ExpressRoute.
  
Ytterligare frågor som måste besvaras för kunder med flera platser i flera olika områden:
  
1. Behöver du en ExpressRoute-krets på varje plats? Om du använder Skype för företag – Online eller om du är orolig för att få svars känslighet för SharePoint Online eller Exchange Online, rekommenderas ett redundant par aktiva/aktiva ExpressRoute-kretsar på varje plats. Se Skype för företag – medie kvalitet och nätverks anslutnings guide för mer information.

2. Om en ExpressRoute-krets inte är tillgänglig i ett visst område kan du använda Office 365 för att cirkulera trafik?

3. Vilken är den bästa metoden för att konsolidera trafik för nätverk med många mindre platser?

De här presenteras som en unik utmaning som kräver att du utvärderar ditt eget nätverk samt de alternativ som är tillgängliga från Microsoft.

|**Bedömning**|**Nätverks komponenter att utvärdera**|
|:-----|:-----|
|Kretsar på mer än en plats  <br/> |Vi rekommenderar minst två kretsar som har kon figurer ATS på ett aktivt/aktivt sätt.  <br/> Kostnad, tids fördröjning och bandbredd måste jämföras.  <br/> Använd BGP-vägs kostnad, PAC-filer och NAT för att hantera routning med flera kretsar.  <br/> |
|Routning från platser utan en ExpressRoute-krets  <br/> |Vi rekommenderar att utgångs-och DNS-matchningen visas som nära den person som initierar begäran för Office 365.  <br/> DNS-vidarebefordran kan användas för att låta fjärranslutna kontor upptäcka lämplig slut punkt.  <br/> Klienter på fjärrkontoret måste vara tillgängliga och ge till gång till ExpressRoute-kretsen.  <br/> |
|Mindre Office-konsolidering  <br/> |Tillgänglig bandbredd och data användning bör övervägas noggrant.  <br/> |

> [!NOTE]
> Microsoft föredrar ExpressRoute över Internet om vägen är tillgänglig oavsett fysisk plats.
  
Varje enskilt övervägande måste beaktas för varje unikt nätverk. Nedan följer ett exempel.
  
### <a name="example-2-multi-geographic-locations"></a>Exempel 2: flera geografiska platser
  
Det här exemplet är ett scenario för ett fiktivt företag som heter Humongous försäkring som har flera geografiska platser.
  
Humongous-försäkring är geografiskt utspridd med kontor över hela världen. De vill implementera Azure ExpressRoute för Office 365 för att behålla majoriteten av deras Office 365-trafik på direkta nätverks anslutningar. Humongous försäkring har också kontor på två extra kontinenter. De anställda på fjärrkontoret där ExpressRoute inte är genomförbart måste omdirigera till en eller båda av de primära funktionerna för att använda en ExpressRoute-anslutning.
  
Med GUID-principen får Office 365 till gång till trafik till ett Microsoft-datacenter så snabbt som möjligt. I det här exemplet måste Humongous försäkring bestämma om deras fjärranslutna kontor ska omdirigeras via Internet för att komma till ett Microsoft-datacenter över alla anslutningar så snabbt som möjligt eller om deras fjärranslutna kontor ska använda ett internt nätverk för att komma till ett Microsoft-datacenter över en ExpressRoute-anslutning så fort som möjligt.
  
Microsofts Data Center, nätverk och program arkitektur är utformade för att ta globalt med olika typer av kommunikation och betjäna dem på det effektivaste sättet. Det här är ett av de största nätverken i världen. Förfrågningar som är avsedda för Office 365 och som finns längre än vad som behövs för att utnyttja denna arkitektur kan inte användas.
  
I Humongous försäkrings fall ska de fortsätta beroende på vilka program de tänker använda över ExpressRoute. Till exempel, om de är en Skype för företag – Online-kund eller planerar att använda ExpressRoute anslutnings barhet när du ansluter till externa Skype för företag – Online-möten, bör du tillhandahålla ytterligare en ExpressRoute-krets för den tredje platsen. Detta kan vara dyrare än ett nätverks perspektiv; Om du dirigerar förfrågningar från en kontinent till en annan innan du levererar till ett Microsoft-datacenter kan det orsaka en dåligt eller oanvändbar upplevelse under möten och kommunikationer med Skype för företag – online.
  
Om Humongous försäkring inte använder eller inte planerar att utnyttja Skype för företag – online på något sätt kan det vara genomförbart att dirigera Office 365 till en kontinent med en ExpressRoute-anslutning. I båda fallen rekommenderas att Internet trafiken till Internet på den lokala webbplatsen fungerar för att utnyttja innehålls leverans nätverken som Office 365 använder.
  
![ExpressRoute multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
När Humongous-försäkring planerar sin strategi för flera geografier finns det ett antal saker du bör tänka på när det gäller kretsen, antalet kretsar, redundans och så vidare.
  
Med ExpressRoute på en enda plats med flera regioner som försöker använda kretsen vill Humongous försäkringar vara säker på att anslutningar till Office 365 från fjärrkontoret skickas till Office 365 Data Center närmaste huvud kontor och tas emot av huvud kontoret. För att göra det här implementerar Humongous försäkring DNS-vidarekoppling för att minska antalet cirkulering och DNS-sökningar som krävs för att upprätta en lämplig anslutning till Office 365-miljön närmast Internet avgångs punkten. Detta förhindrar klienten från att lösa en lokal front Server och ser till att front servern som personen ansluter till är nära huvud kontoret där Humongous försäkring är peering with Microsoft. Du kan också använda [en villkorlig vidarebefordrare för ett domän namn](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx).
  
I det här scenariot kommer trafik från fjärrkontoret att matcha front infrastrukturen för Office 365 i Nord Amerika och utnyttja Office 365 för att ansluta till backend-servrarna enligt arkitekturen för Office 365-programmet. Till exempel skulle Exchange Online säga upp anslutningen i Nord Amerika och dessa front servrar ansluter till backend-postservern där klient organisationen bor. Alla tjänster har en mycket fördelad front dörr tjänst med unicast-och anycast-destinationer.
  
Om Humongous har huvud kontor i flera kontinenter rekommenderas minst två aktiva/aktiva kretsar per region för att minska svars tiden för känsliga program som Skype för företag – online. Om alla kontor är i en enda kontinent, eller om du inte använder real tids samarbete, är ett kundspecifika beslut att få ett kundbaserat eller distribuerat avsluts punkt. När flera kretsar är tillgängliga säkerställer BGP-routning redundans att en enda krets inte är tillgänglig.
  
Läs mer om exempel på [arbetsflödeskonfigurationer](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) och [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Selektiv routning med ExpressRoute

Selektiv routning med ExpressRoute kan krävas av en mängd olika anledningar, till exempel testning, som utsätter ExpressRoute till en delmängd användare. Det finns olika verktyg som kunder kan använda för att selektivt dirigera Office 365-nätverks trafik via ExpressRoute:
  
1. **Routing filter/åtskillnad** -tillåta BGP-vägar till Office 365 via ExpressRoute till en delmängd av dina undernät eller routrar. Det här är ett selektivt sätt att cirkulera nätverks segment eller fysiska kontor. Det här är vanligt för att sprida ExpressRoute för Office 365 och är konfigurerat på BGP-enheter.

2. **PAC-filer/URL-adresser** – dirigerar Office 365 till nätverks trafik för specifika FQDN-namn för att dirigera på en specifik sökväg. Det här är ett selektivt sätt att cirkulera klient datorer som identifieras vid [distribution av PAC-filer](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies).

3. **Flödes filtrering**  -  [Väg filter](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) är ett sätt att förbruka en delmängd av tjänster som stöds genom Microsoft peering.

4. **BGP-communities** -filtrering baserad på [BGP community-Taggar](https://aka.ms/bgpexpressroute365) låter en kund avgöra vilka Office 365-program som ska passera ExpressRoute och vilka som ska passera Internet.

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
## <a name="related-topics"></a>Närliggande ämnen

[Utvärdering av Office 365 nätverks anslutning](assessing-network-connectivity.md)
  
[Azure ExpressRoute för Office 365](azure-expressroute.md)
  
[Hantera ExpressRoute för Office 365](managing-expressroute-for-connectivity.md)
  
[Nätverks planering med ExpressRoute för Office 365](network-planning-with-expressroute.md)
  
[Implementera ExpressRoute för Office 365](implementing-expressroute.md)
  
[Media kvalitet och nätverks anslutnings prestanda i Skype för företag – Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimera ditt nätverk för Skype för företag – Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute och QoS i Skype för företag – Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Samtals flöde med ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Använda BGP-communities i ExpressRoute för Office 365](bgp-communities-in-expressroute.md)
  
[Prestanda justering för Office 365 med bas linjer och prestanda historik](performance-tuning-using-baselines-and-history.md)
  
[Plan för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md)
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-nätverks-och prestanda inställning](network-planning-and-performance.md)
