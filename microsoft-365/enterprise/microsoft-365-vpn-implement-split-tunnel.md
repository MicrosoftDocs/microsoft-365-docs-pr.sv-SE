---
title: Implementera VPN-delade tunnlar för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Så här implementerar du VPN-delade tunnlar för Office 365
ms.openlocfilehash: 2feb03f2142639a1c1de4ff9a69768e23f282546
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924230"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>Implementera VPN-delade tunnlar för Office 365

>[!NOTE]
>Det här avsnittet är en del av en uppsättning avsnitt som handlar om Office 365-optimering för fjärranvändare.
>- En översikt över hur du använder VPN-delade tunnlar för att optimera Office 365-anslutningar för fjärranslutna användare finns i Översikt: VPN-delade tunnlar för [Office 365.](microsoft-365-vpn-split-tunnel.md)
>- Information om hur du optimerar prestanda i globala klientorganisationen för Office 365 för användare i Kina finns i [Prestandaoptimering i Office 365 för användare i Kina.](microsoft-365-networking-china.md)

Under många år har företag använt VPN för att stödja distansupplevelser för sina användare. Även om det fortfarande finns grundläggande arbetsbelastningar lokalt var en VPN från den fjärranslutna klienten via ett datacenter i företagsnätverket den primära metoden för fjärranslutna användare att få åtkomst till företagets resurser. För att skydda dessa anslutningar bygger företag lager av nätverkssäkerhetslösningar längs VPN-sökvägarna. Detta gjordes för att skydda den interna infrastrukturen samt för att skydda mobil surfning av externa webbplatser genom att omdirigera trafik till VPN och sedan ut genom den lokala Internet perimeter. VPN, nätverkskretsar och tillhörande säkerhetsinfrastruktur har ofta skapats och skalats för en definierad trafikvolym, vanligtvis med majoriteten av anslutningarna initierade från företagsnätverket och de flesta av dem stannar inom de interna nätverksgränserna.

Under ganska lång tid har VPN-modeller där alla anslutningar från fjärranvändarenheten åter dirigerats tillbaka till det lokala nätverket (kallas tvingade **tunnlar**) varit till stor del mindre, så länge den samtidiga skalan för fjärranvändare var liten och trafikvolym genom VPN var låg.  Vissa kunder fortsätter att använda VPN-tvingad tunneling som statuskvot även efter att deras program flyttats från företagets perimeter till offentliga SaaS-moln, vilket Office 365 är ett utmärkt exempel.

Användningen av tvingade VPN för att ansluta till distribuerade och prestandaberoende molnprogram är extremt suboptimerad, men den negativa effekten av detta kan ha accepterats av vissa företag för att bibehålla statuskvot ur säkerhetsperspektiv. Ett exempeldiagram över det här scenariot visas nedan:

![VPN-konfiguration för delade tunnlar](../media/vpn-split-tunneling/enterprise-network-traditional.png)

Det här problemet har ökat i flera år, och många kunder har rapporterat en betydande förändring av nätverkstrafikmönster. Trafik som brukade hålla sig lokal ansluter nu till externa molnslutpunkter. Flera Microsoft-kunder rapporterar att cirka 80 % av deras nätverkstrafik tidigare var till en intern källa (som representeras av den prickade linjen i diagrammet ovan). År 2020 är antalet nu omkring 20 % eller lägre eftersom de har skiftat stora arbetsbelastningar till molnet, de här trenderna är inte ovanligt med andra företag. Med tiden blir ovanstående modell krånglig och oanvändbar allt eftersom molnet fortskrider, och organisationen hindras från att vara agile när de flyttar till en första värld av molnet.

Den globala COVID-19-krislösningen har eskalerat problemet så att det omedelbart måste åtgärdas. Behovet av att säkerställa att personalens säkerhet har genererat krav på företags-IT för att stödja arbete hemifrån i en enorm skala. Microsoft Office 365 har en bra position för att hjälpa kunder att uppfylla detta behov, men hög samtidighet för användare som arbetar hemifrån genererar en stor volym Office 365-trafik som, om de dirigeras genom tvingad VPN-tunnel och lokala nätverkskretsar, leder till en snabb mättnad och kör VPN-infrastrukturen ur kapaciteten. I den här nya verkligheten är det inte längre bara ett hinder för prestanda att använda VPN för att komma åt Office 365, utan en hård vägg som inte bara påverkar Office 365 utan kritiska affärsåtgärder som fortfarande måste förlita sig på VPN för drift.

Microsoft har i många år arbetat tillsammans med kunder och den bredare branschen för att tillhandahålla effektiva och moderna lösningar på problemen från våra egna tjänster och för att följa branschens bästa praxis. [Anslutningsprinciper](./microsoft-365-network-connectivity-principles.md) för Office 365-tjänsten har utformats för att fungera effektivt för fjärranvändare medan de fortfarande tillåter att en organisation upprätthåller säkerhet och kontroll över anslutningarna. De här lösningarna kan också implementeras mycket snabbt med begränsat arbete men få betydande positiv inverkan på problemen som beskrivs ovan.

Microsofts rekommenderade strategi för att optimera distansarbetares anslutning fokuserar på att snabbt minska problemen med den traditionella metoden och även ge hög prestanda med några få enkla steg. Dessa steg justerar den äldre VPN-metoden för ett litet antal definierade slutpunkter som kringgår flaskhalsar i VPN-servrar. En motsvarande eller till och med överordnad säkerhetsmodell kan användas på olika lager för att ta bort behovet av att skydda all trafik på företagets nätverk som utgående. I de flesta fall kan detta uppnås effektivt inom några timmar och sedan kan skalbara till andra arbetsbelastningar eftersom behov och tidskrav tillåter det.

## <a name="common-vpn-scenarios"></a>Vanliga VPN-scenarier

I listan nedan ser du de vanligaste VPN-scenarierna som visas i företagsmiljöer. De flesta kunder använder standard 1 (VPN-tvingade tunnel). Det här avsnittet hjälper dig att snabbt och säkert gå över till modell **2**, som kan nås med relativt lite ansträngning, och har stora fördelar för nätverksprestanda och användarupplevelse.

| **Modell** | **Beskrivning** |
| --- | --- |
| [1. VPN-tvingade tunnel](#1-vpn-forced-tunnel) | 100 % av trafiken går in i VPN-tunnel, inklusive lokal, Internet och all O365/M365 |
| [2. VPN-tvingade tunnel med få undantag](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN-tunnel används som standard (standard routepunkter till VPN), med få, viktigast undantagna scenarier som tillåts gå direkt |
| [3. VPN-tvingade tunnlar med breda undantag](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN-tunnel används som standard (standard routepunkter till VPN), med breda undantag som tillåts gå direkt (till exempel alla Office 365, All Salesforce, All zoom) |
| [4. VPN selektiv tunnel](#4-vpn-selective-tunnel) | VPN-tunnel används endast för corpnet-baserade tjänster. Standard route (Internet och alla internetbaserade tjänster) dirigeras direkt. |
| [5. Ingen VPN](#5-no-vpn) | En variant av #2, där alla corpnet-tjänster publiceras med moderna säkerhetsmetoder (t.ex. Zscaler ZPA, Azure Active Directory (Azure AD) Proxy/MCAS osv.) |

### <a name="1-vpn-forced-tunnel"></a>1. VPN-tvingade tunnel

Det här är det vanligaste startscenariot för de flesta företagskunder. En tvingade VPN används, vilket innebär att 100 % av trafiken dirigeras till företagsnätverket oavsett det faktum att slutpunkten finns inom företagsnätverket eller inte. All extern (Internet)bunden trafik, till exempel Office 365 eller Internetsurfning, plockas sedan bort från den lokala säkerhetsutrustningen, till exempel proxy. Under den aktuella situationen där nästan 100 % av användarna arbetar på distans lägger den här modellen därför extremt hög belastning på VPN-infrastrukturen och riskerar att avsevärt hindra prestanda för all företagstrafik och därmed kan företaget agera effektivt vid en krissituation.

![VPN-tvingade tunnelmodell 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN-tvingade tunnlar med ett litet antal betrodda undantag

Den här modellen är avsevärt mer effektiv om ett företag använder den, eftersom den tillåter ett litet antal kontrollerade och definierade slutpunkter som är mycket hög belastning och svarstider som är känsliga för att kringgå VPN-tunneln och gå direkt till Office 365-tjänsten i det här exemplet. Detta förbättrar avsevärt prestandan för offloaded-tjänsterna och minskar också belastningen på VPN-infrastrukturen, vilket gör att element som fortfarande kräver att det fungerar med lägre innehåll för resurser minskar. Det är den här modellen som den här artikeln koncentrerar sig på att hjälpa till med övergången till, eftersom det möjliggör att enkla, definierade åtgärder vidtas mycket snabbt med många positiva resultat.

![Split Tunnel VPN modell 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN-tvingade tunnlar med breda undantag

Den tredje modellen breddar omfattningen av modell två så att den inte bara skickar en liten grupp definierade slutpunkter direkt, utan skickar i stället all trafik direkt till betrodda tjänster som Office 365 och SalesForce. Det här minskar ytterligare belastningen på företagets VPN-infrastruktur och förbättrar prestandan för de definierade tjänsterna. Eftersom det troligtvis tar längre tid att utvärdera genomförbarheten för och implementera den här modellen, är det sannolikt ett steg som kan genomföras iterativt vid ett senare tillfälle när två modellen har implementerats.

![Split Tunnel VPN model 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN-selektiv tunnel

Den här modellen vänder den tredje modellen då endast trafik som identifieras som har en företags-IP-adress skickas nedåt genom VPN-tunneln och därmed är Internetsökvägen standardrutten för allt annat. Den här modellen kräver att organisationen är bra på vägen till [Noll](https://www.microsoft.com/security/zero-trust?rtc=1) förtroende för att kunna implementera den här modellen på ett säkert sätt. Observera att denna modell eller någon variant kommer att bli nödvändig standard med tiden allt eftersom fler och fler tjänster försvinner från företagsnätverket och till molnet. Microsoft använder den här modellen internt. Du kan hitta mer information om Microsofts implementering av VPN-delade tunnlar vid körning av VPN: Hur Microsoft håller [sin fjärranslutna arbetsstyrka ansluten.](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

![Vpn-modell för delade tunnlar 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. Ingen VPN

En mer avancerad version av modell nummer två där alla interna tjänster publiceras med en modern säkerhets metod eller SDWAN-lösning som Azure AD-proxy, MCAS, Zscaler ZPA osv.

![Split Tunnel VPN modell 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>Implementera VPN-delade tunnlar

I det här avsnittet hittar du de enkla steg som krävs för att migrera din VPN-klientarkitektur från en _VPN-tvingade tunnel_ till en _VPN-tvingade tunnel_ med ett litet antal betrodda undantag – VPN-modell för delade [tunnlar #2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) i avsnittet om vanliga [VPN-scenarier.](#common-vpn-scenarios)

Diagrammet nedan illustrerar hur den rekommenderade VPN-delade tunnellösningen fungerar:

![Detaljer om VPN-lösningen för delade tunnlar](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. Identifiera slutpunkterna som ska optimeras

I avsnittet url-adresser och IP-adressintervall för [Office 365](urls-and-ip-address-ranges.md) identifierar Microsoft tydligt de viktiga slutpunkter som du behöver för att optimera och kategoriserar dem som **Optimera.** Det finns för närvarande bara fyra URL:er och tjugo IP-undernät som måste optimeras. Denna lilla grupp med slutpunkter står för cirka 70 –80 % av trafiken till Office 365-tjänsten, inklusive latenskänsliga slutpunkter, till exempel de för Teams-media. I princip är det den trafik som vi behöver ta extra hand om, och det är också trafiken som kommer att få otroligt tryck på traditionella nätverksvägar och VPN-infrastrukturen.

URL:er i den här kategorin har följande egenskaper:

- Microsoft ägda och hanterade slutpunkter som finns på Microsofts infrastruktur
- Har IP-adresser tillhandahållit
- Låg förändringshastighet och förväntas vara liten i antal (för närvarande 20 IP-undernät)
- Är bandbredd och/eller svarstidskänsliga
- Kan ha obligatoriska säkerhetselement som tillhandahålls i tjänsten i stället för infogade i nätverket
- Står för cirka 70–80 % av trafiken till Office 365-tjänsten

Mer information om Office 365-slutpunkter och hur de kategoriseras och hanteras finns i artikeln Hantera [Office 365-slutpunkter.](managing-office-365-endpoints.md)

#### <a name="optimize-urls"></a>Optimera URL:er

Aktuella optimera-URL:er finns i tabellen nedan. I de flesta fall bör du bara behöva använda URL-slutpunkter i en webbläsares [PAC-fil](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) där slutpunkterna är konfigurerade att skickas direkt, snarare än till proxyn.

| Optimera URL:er | Port/Protokoll | Syfte |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Det här är en av de primära WEBBADRESSerna som Outlook använder för att ansluta till Sin Exchange Online-server och har en stor volym bandbreddsanvändning och antal anslutningar. Låg nätverksfördröjning krävs för onlinefunktioner, bland annat: snabbsökning, andra postlådekalendrar, ledig/upptagen-sökning, hantering av regler och aviseringar, Exchange online-arkiv, e-postmeddelanden avgående utkorgen. |
| <https://outlook.office.com> | TCP 443 | Den här URL-adressen används för Outlook Online Web Access vid anslutning till Exchange Online-servern och är känslig för nätverksfördröjning. Anslutningar krävs särskilt för stora filuppladdningar och nedladdning med SharePoint Online. |
| https:// \<tenant\> .sharepoint.com | TCP 443 | Det här är den primära URL-adressen för SharePoint Online och har hög bandbreddsanvändning. |
| https:// \<tenant\> -my.sharepoint.com | TCP 443 | Det här är den primära URL:en för OneDrive för företag och har hög bandbreddsanvändning och eventuellt högt anslutningsantal från synkroniseringsverktyget för OneDrive för företag. |
| Teams Media-IP (ingen URL) | UDP 3478, 3479, 3480 och 3481 | Tilldelning av reläidentifiering och realtidstrafik (3478), ljud (3479), video (3480) och videoskärmdelning (3481). Det här är slutpunkterna som används för Skype för företag- och Microsoft Teams Media-trafik (samtal, möten o.s.v.). De flesta slutpunkter tillhandahålls när Microsoft Teams-klienten upprättar ett samtal (och finns i de ip-adresser som krävs för tjänsten). Användning av UDP-protokollet krävs för optimal mediakvalitet.   |

I exemplen ovan bör **klientorganisationen** ersättas med ditt klientnamn för Office 365. Skulle till exempel **contoso.onmicrosoft.com** använda _contoso.sharepoint.com_ och _constoso-my.sharepoint.com_.

#### <a name="optimize-ip-address-ranges"></a>Optimera IP-adressintervall

När du skriver de IP-intervall som dessa slutpunkter motsvarar är följande. Vi  rekommenderar starkt att [](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) du använder ett skript som det här exemplet, [Office 365-IP-](microsoft-365-ip-web-service.md) och URL-webbtjänsten eller [URL/IP-sidan](urls-and-ip-address-ranges.md) för att söka efter uppdateringar när du använder konfigurationen, och att tillämpa en princip regelbundet.

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
191.234.140.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. Optimera åtkomsten till dessa slutpunkter via VPN

Nu när vi har identifierat dessa kritiska slutpunkter måste vi dirigera om dem från VPN-tunneln och göra det möjligt för dem att använda användarens lokala Internetanslutning för att ansluta direkt till tjänsten. Hur detta sker varierar beroende på VPN-produkten och maskinplattformen som används, men de flesta VPN-lösningar tillåter att viss enkel konfiguration av principen använder den här logiken. Information om VPN-plattformsspecifik vägledning för delade tunnlar finns [i HOWTO-guider för vanliga VPN-plattformar.](#howto-guides-for-common-vpn-platforms)

Om du vill testa lösningen manuellt kan du köra följande PowerShell-exempel för att efterlikna lösningen på routetabellnivån. I det här exemplet läggs en route till för varje Teams Media IP-undernät i routetabellen. Du kan testa Teams medieprestanda före och efter samt se differensen mellan routes för de angivna slutpunkterna.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Exempel: Lägg till IP-undernät för Teams Media i routetabellen

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

I skriptet ovan är _$intIndex_ indexet för gränssnittet som är anslutet till internet (genom att köra **get-netadapter** i PowerShell, leta efter värdet för _ifIndex_) och _$gateway_ är standardgatewayen för det gränssnittet (hitta genom att köra **ipconfig** i en kommandotolk eller **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway). NextHop** i PowerShell).

När du har lagt till routes kan du bekräfta  att tabellen för routen är korrekt genom att köra routeutskriften i en kommandotolk eller PowerShell. Utdata bör innehålla de routes du har lagt till, med gränssnittsindexet _(22_ i det här exemplet) och gatewayen för gränssnittet _(192.168.1.1_ i det här exemplet):

![Utskrift av färdväg](../media/vpn-split-tunneling/vpn-route-print.png)

Om du  vill lägga till routes för alla aktuella IP-adressintervall i kategorin Optimera kan du använda följande skriptvariant för att fråga [OFFICE 365 IP-](microsoft-365-ip-web-service.md) och URL-webbtjänsten för den aktuella uppsättningen optimera IP-undernät och lägga till dem i routetabellen.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Exempel: Lägg till alla Optimera-undernät i routetabellen

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

Om du oavsiktligt har lagt till routes med felaktiga parametrar eller bara vill återställa ändringarna kan du ta bort de vägar som du just lagt till med följande kommando:

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

VPN-klienten ska konfigureras så att  trafiken till optimerings-IP:erna dirigeras på det här sättet. Det gör att trafiken kan använda lokala Microsoft-resurser, till exempel Office 365-tjänste fram dörrar som [Azure Front Door](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) som levererar Office 365-tjänster och anslutningsslutpunkter så nära dina användare som möjligt. Det gör att vi kan leverera extremt höga prestandanivåer till användare oavsett var de befinner sig i världen och utnyttja [Microsofts](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)globala nätverk , vilket troligen ligger inom ett litet antal millisekunder av användarnas direkta utgång.

## <a name="configuring-and-securing-teams-media-traffic"></a>Konfigurera och skydda Teams mediatrafik

Vissa administratörer kan kräva mer detaljerad information om hur samtalsflöden fungerar i Teams med en modell för delade tunnlar och hur anslutningar skyddas.

### <a name="configuration"></a>Konfiguration

För både samtal och möten, så länge som krävs Optimera IP-undernät för Teams-media är [](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) korrekt på plats i routetabellen, kommer det lokala gränssnittet att returneras för Microsofts destinationer i Microsofts IP-block som anges ovan när Teams anropar funktionen Optimera IP-undernät för Teams-media.

Vissa VPN-klientprogram tillåter routing-manipulering baserat på URL. Men Teams mediatrafik har ingen URL kopplad till det, så kontroll av dirigering för denna trafik måste göras med hjälp av IP-undernät.

I vissa fall, ofta utan anknytning till Teams klientkonfiguration, passerar mediatrafiken VPN-tunneln även om rätt vägar är på plats. Om det här scenariot uppstår bör det vara tillräckligt att använda en brandväggsregel för att blockera Teams IP-undernät eller portar från att använda VPN.

>[!IMPORTANT]
>För att säkerställa att Teams mediatrafik dirigeras via den önskade metoden i alla VPN-scenarier bör du se till att användarna kör Microsoft Teams klient version **1.3.00.13565** eller senare. Den här versionen innehåller förbättringar i hur klienten identifierar tillgängliga nätverkssökvägar.

Signaltrafiken utförs via HTTPS och är inte lika latenskänslig som  mediatrafiken och markeras som Tillåt i URL/IP-data och kan därför med säkerhet dirigeras genom VPN-klienten om du vill.

### <a name="security"></a>Säkerhet

Ett vanligt argument för att undvika delade tunnlar är att det är mindre säkert att göra det, det vill säga Trafik som inte går genom VPN-tunneln kommer inte att dra nytta av det krypteringsschema som tillämpas på VPN-tunneln, och är därför mindre säker.

Huvudargumentet till det här är att mediatrafiken redan är krypterad via _SRTP (Secure Real-Time Transport Protocol),_ en profil hos Real-Time Transport Protocol (RTP) som ger skydd mot RTP-trafik av konfidentiell information, autentisering och uppspelning av attackskydd. SRTP förlitar sig på en slumpmässigt genererad sessionsnyckel, som utbyts via TLS-säkrad signalkanal. Mer detaljerad information finns i den här [säkerhetsguiden, men](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)det primära avsnittet av intresse är mediekryptering.

Mediatrafiken krypteras med SRTP, som använder en sessionsnyckel som genereras av en säker slumpgenerator och utbyts med den TLS-kanal som signalerar. Dessutom krypteras även media som flyter i båda riktningarna mellan medlingsservern och dess interna nästa hopp med SRTP.

Skype för företag – Online genererar användarnamn och lösenord för säker åtkomst till medierelä över _Traversal Med reläer runt NAT (TURN)_. Media vidarebefordrar användarnamnet/lösenordet via en TLS-skyddad SIP-kanal. Det är värt att notera att även om en VPN-tunnel kan användas för att ansluta klienten till företagsnätverket måste trafiken fortfarande flöda i SRTP-formuläret när den lämnar företagsnätverket för att nå tjänsten.

Information om hur Teams minimerar vanliga säkerhetsproblem, t.ex. röst- eller session _traversal-verktyg för NAT (STUN)_ -amplification-attacker, finns i [den här artikeln.](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)

Du kan också läsa om moderna säkerhetskontroller i scenarier med distansarbete under Alternativa sätt för säkerhetsexperter och IT-personal för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbetesscenarier [(Microsoft Security Team-bloggen).](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="testing"></a>Testning

När principen är på plats bör du kontrollera att den fungerar som förväntat. Det finns flera sätt att testa sökvägen är korrekt inställd för att använda den lokala Internetanslutningen:

- Kör [Microsoft 365-anslutningstestet](https://aka.ms/netonboard) som kör anslutningstester åt dig, inklusive spårningsvägar som ovan. Vi lägger även till VPN-tester i det här verktyget som också bör ge ytterligare insikter.

- En enkel spårning till en slutpunkt inom omfattningen för den delade tunneln bör visa den bana som tagits, till exempel:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  Sedan bör du se en sökväg via den lokala Internetleverantören till den här slutpunkten som bör matcha till en IP i Teams-intervallen som vi har konfigurerat för delade tunnlar.

- Ta en nätverksinspelning med hjälp av ett verktyg som Wireshark. Filtrera på UDP under ett samtal så bör du se trafiken gå till en IP i intervallet Teams **optimera.** Om VPN-tunneln används för den här trafiken kommer mediatrafiken inte att visas i spårningen.

### <a name="additional-support-logs"></a>Ytterligare supportloggar

Om du behöver ytterligare data för felsökning, eller om du begär hjälp från Microsoft Support, bör du använda följande information för att snabbt hitta en lösning. Microsoft support's **TSS Windows CMD-baserade universal TroubleShooting Script toolset** kan hjälpa dig att samla in relevanta loggar på ett enkelt sätt. Verktyget och instruktionerna för användning finns på <https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>HOWTO-guider för vanliga VPN-plattformar

Det här avsnittet innehåller länkar till detaljerade instruktioner för implementering av delade tunnlar för Office 365-trafik från de vanligaste partners i det här utrymmet. Vi kommer att lägga till ytterligare guider när de blir tillgängliga.

- **Windows 10 VPN-klient**: Optimera Office 365-trafik för fjärranslutna medarbetare [med den inbyggda Windows 10 VPN-klienten](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**: [Optimera alla koppla ihop delade tunnlar för Office365](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo GlobalProtect**: Optimera [Office 365-trafik via VPN-delade tunnel utesluter åtkomstväg](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**: [Optimera Office 365-trafik](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365) på fjärråtkomst via VPN när big-IP APM används
- **Citrix Gateway:** [Optimera Citrix Gateway VPN-delad tunnel för Office365](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure:** [VPN-tunnlar: Konfigurera delade tunnlar för att utesluta Office365-program](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **Kontrollpunkt VPN:** [Konfigurera delade tunnlar för Office 365 och andra SaaS-program](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>Vanliga frågor och svar

Microsofts säkerhetsteam har [publicerat](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) en artikel som beskriver viktiga sätt för säkerhetsexperter och IT-personal kan uppnå moderna säkerhetskontroller i dagens unika fjärrarbetesscenarier. Nedan finns dessutom några vanliga kundfrågor och svar om det här ämnet.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Hur gör jag för att hindra användare från att komma åt andra klientorganisationar som jag inte litar på där de kan föra ut data?

Svaret är en funktion [som kallas klientbegränsningar.](/azure/active-directory/manage-apps/tenant-restrictions) Autentiseringstrafiken är inte hög volym eller särskilt latenskänslig, så kan skickas via VPN-lösningen till den lokala proxy där funktionen används. En lista över betrodda klientorganisationen behålls här och om klienten försöker hämta en token till en klientorganisation som inte är betrodd nekas bara begäran av proxyn. Om klientorganisationen är betrodd blir en token tillgänglig om användaren har rätt autentiseringsuppgifter och rättigheter.

Så även om en användare kan upprätta en TCP/UDP-anslutning till optimera markerade slutpunkter ovan, utan en giltig token för att komma åt den aktuella klientorganisationen, kan de helt enkelt inte logga in och komma åt/flytta data.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Tillåter den här modellen åtkomst till konsumenttjänster som privata OneDrive-konton?

Nej, Office 365-slutpunkterna är inte samma som konsumenttjänsterna (Onedrive.live.com som exempel) vilket innebär att delade tunnlar inte gör det möjligt för en användare att få direkt åtkomst till konsumenttjänster. Trafik till konsumentslutpunkter fortsätter att använda VPN-tunneln och befintliga principer fortsätter att tillämpas.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Hur tillämpar jag DLP och skyddar känsliga data när trafiken inte längre går via min lokala lösning?

Office 365 har en omfattande uppsättning inbyggda verktyg som hjälper dig att förhindra att känslig information [lämnas ut av misstag.](../compliance/data-loss-prevention-policies.md) Du kan använda de inbyggda [DLP-funktionerna](../compliance/data-loss-prevention-policies.md) i Teams och SharePoint för att identifiera olämplig lagrad eller delad känslig information. Om en del av din strategi för distansarbete omfattar en BYOD-princip (Bring-Your-Own-Device) kan du använda [programbaserad](/azure/active-directory/conditional-access/app-based-conditional-access) villkorsstyrd åtkomst för att förhindra att känsliga data laddas ned till användarnas personliga enheter

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Hur utvärderar och behåller jag kontrollen över användarens autentisering när de ansluter direkt?

Utöver funktionen för klientbegränsningar som [](/azure/active-directory/conditional-access/overview) anges i Kv1 kan villkorsstyrda åtkomstprinciper tillämpas för att dynamiskt bedöma risken med en autentiseringsbegäran och reagera på ett lämpligt sätt. Microsoft rekommenderar att [zero trust-modellen](https://www.microsoft.com/security/zero-trust?rtc=1) implementeras med tiden och vi kan använda villkorsstyrda åtkomstpolicyer för Azure AD för att behålla kontrollen i en första värld med mobil och moln. Villkorsstyrda åtkomstprinciper kan användas för att fatta ett beslut i realtid om en autentiseringsbegäran ska lyckas baserat på flera faktorer, till exempel:

- Enhet, är enheten känd/betrodd/domän ansluten?
- IP – kommer autentiseringsbegäran från en känd företags-IP-adress? Eller från ett land som vi inte litar på?
- Program – Har användaren behörighet att använda det här programmet?

Sedan kan vi utlösa principer som att godkänna, utlösa MFA eller blockera autentisering baserat på dessa principer.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Hur skyddar jag mot virus och skadlig programvara?

Office 365 skyddar som återigen de optimerade slutpunkterna i olika lager i själva tjänsten, [som beskrivs i det här dokumentet.](/office365/Enterprise/office-365-malware-and-ransomware-protection) Som vi har nämnt är det mycket mer effektivt att tillhandahålla dessa säkerhetselement i själva tjänsten i stället för att försöka göra det i nivå med enheter som inte helt förstår protokollen/trafiken. Som standard söker SharePoint Online [automatiskt igenom filuppladdningar efter](../security/office-365-security/virus-detection-in-spo.md) känd skadlig programvara

För Exchange-slutpunkterna som anges ovan [gör Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) och Microsoft Defender för Office [365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) ett utmärkt sätt att tillhandahålla säkerheten för trafiken till tjänsten.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Kan jag skicka mer än bara optimera trafik direkt?

Prioritet bör ges till optimera **markerade** slutpunkter eftersom dessa ger största möjliga fördelar för en låg arbetsnivå. Men om du vill måste tillåta markerade slutpunkter för att tjänsten ska fungera och se till att IP-adresser tillhandahålls för slutpunkterna som kan användas om det behövs.

Det finns även olika leverantörer som erbjuder molnbaserade proxy/säkerhetslösningar som kallas säkra webbgateway som tillhandahåller central säkerhet, kontroll- och företagspolicyprogram för allmän webbsurfning. De här lösningarna kan fungera bra i en molnbaserad första värld, om de är tillgängliga i hög grad, utför och etableras nära dina användare genom att tillåta att säker Internetanslutning levereras från en molnbaserad plats nära användaren. Det här tar bort behovet av hårnålsnätverk via VPN/företagsnätverket för allmän webbtrafik, samtidigt som central säkerhetskontroll fortfarande tillåts.

Även med de här lösningarna rekommenderar Microsoft dock starkt att optimera markerad Office 365-trafik skickas direkt till tjänsten.

Råd om hur du tillåter direkt åtkomst till ett virtuellt Azure-nätverk finns i artikeln Fjärrarbete med [Azure VPN Gateway punkt-till-webbplats.](/azure/vpn-gateway/work-remotely-support)

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Varför krävs port 80? Skickas trafiken i tydlig trafik?

Port 80 används endast för sådant som omdirigering till en port 443-session, inga kunddata skickas eller är tillgänglig via port 80. [I den](../compliance/encryption.md) här artikeln beskrivs kryptering för data som överförs [](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) och vilan för Office 365, och i den här artikeln beskrivs hur vi använder SRTP för att skydda Teams mediatrafik.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>Gäller detta för användare i Kina som använder en global instans av Office 365?

**Nej,** det har den inte. Den ena varningen till ovanstående är användare i Folkrepubliken Kina som ansluter till en global instans av Office 365. På grund av den vanliga förekomsten av nätverksstockningar mellan kantlinjer i regionen kan direkt utgående Internet-prestanda variera. De flesta kunder i regionen använder VPN för att få fram trafiken till företagsnätverket och använda sin auktoriserade MPLS-krets eller liknande för att gå utanför landet via en optimerad väg. Mer information finns i artikeln om [prestandaoptimering för Office 365 för användare i Kina.](microsoft-365-networking-china.md)

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>Fungerar konfiguration av delade tunnlar för Teams som körs i en webbläsare?

**Nej,** det har den inte. Det fungerar endast på Microsoft Teams klientversion 1.3.00.13565 eller senare. Den här versionen innehåller förbättringar i hur klienten identifierar tillgängliga nätverkssökvägar.

## <a name="related-topics"></a>Relaterade ämnen

[Översikt: VPN-delade tunnlar för Office 365](microsoft-365-vpn-split-tunnel.md)

[Office 365-prestandaoptimering för kinaanvändare](microsoft-365-networking-china.md)

[Alternativa sätt för säkerhetsexperter och IT-personal för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbete (Microsofts blogg om säkerhetsteam)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Förbättra VPN-prestanda på Microsoft: använda Windows 10 VPN-profiler för att tillåta automatiska anslutningar](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Kör på VPN: Så här håller Microsoft sin fjärranslutna arbetsstyrka ansluten](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)

[Office 365 nätverks- och prestandajustering](network-planning-and-performance.md)