---
title: Implementera VPN-fildelning för Office 365
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
description: Så här implementerar du delade VPN-tunnlar för Office 365
ms.openlocfilehash: 4a7c2a18ae5d4f275210ddeaea90eb1bb9bc1f16
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846994"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>Implementera VPN-fildelning för Office 365

>[!NOTE]
>Det här avsnittet är en del av en uppsättning ämnen som riktar sig till Office 365-optimering för fjärran vändare.
>- En översikt över hur du kan använda delnings tunnlar för att optimera Office 365-anslutningar för fjärranslutna användare finns i [Översikt: dela tunnlar för office 365](microsoft-365-vpn-split-tunnel.md).
>- Information om hur du optimerar Office 365 global klient prestanda för användare i Kina finns i [prestanda optimering för office 365 för Kina-användare](microsoft-365-networking-china.md).

För många år som företag har haft stöd för fjärrupplevelser till sina användare. Medan kärn arbets belastningarna befann sig lokalt, var en VPN-anslutning från fjärrklienten via ett Data Center i företags nätverket den primära metoden för fjärran vändare att få till gång till företagets resurser. För att skydda dessa anslutningar skapar företag lager av nätverks säkerhets lösningar längs VPN-vägarna. Detta skedde för att skydda den interna infrastrukturen, samt för att skydda mobil surfning av externa webbplatser genom att dirigera om trafik till VPN och sedan från lokal Internet-perimeter. VPN, nätverks gränser och tillhör ande säkerhets infrastruktur är ofta utformade och skal för en viss trafik, vanligt vis med de flesta anslutningar som initieras från företags nätverket, och de flesta av dem håller sig inom de interna nätverks gränserna.

För ganska lite tid är VPN-modeller där alla anslutningar från fjär renheten routas till det lokala nätverket (kallas **tvingande tunnel trafik** ) var i stort hållbart så länge som fjärran vändare samtidigt var liten och trafik volymerna som passerar VPN-tjänsten låg.  Vissa kunder fortsatte att använda VPN-tvingande tunnlar som status quo även efter att deras program flyttats från företags omkrets till offentliga SaaS-moln är Office 365 ett primtal-exempel.

Det är väldigt optimalt att använda tvingande tunnel anslutningar för att ansluta till distribuerade och prestanda känsliga moln tillämpningar, men den negativa påverkan av detta kan ha godkänts av vissa företag, så att du bevarar statusen quo från ett säkerhets perspektiv. Ett exempel diagram för det här scenariot visas nedan:

![VPN-konfiguration för delad tunnel](../media/vpn-split-tunneling/enterprise-network-traditional.png)

Det här problemet har växandets för ett antal år, med många kunder som rapporterar en större nätverks trafik. Trafik som används för lokal anslutning ansluter nu till externa moln slut punkter. Många Microsoft-kunder rapporterar att tidigare, runt 80% av nätverks trafiken var till en intern källa (representerade av den prickade linjen i ovanstående diagram). I 2020 det numret är nu cirka 20% eller lägre när de har förflyttade stora arbets belastningar till molnet, är dessa trender inte ovanliga med andra företag. Över tiden blir modellen ovan allt mer besvärlig och unhållbart, vilket gör att en organisation inte kan bli smidig när den flyttas till ett moln först världen.

Den globala COVID-19 krisen har eskalerat detta problem för att kräva omedelbar reparation. Behovet att säkerställa att den anställdas säkerhet har genererat ett oöverträffat behov på företaget för att stödja arbete från Home-produktivitet på en enorm nivå. Microsoft Office 365 är välorganiserat för att hjälpa kunder att uppfylla kraven, men hög concurrency för användare som arbetar hemifrån skapar en stor volym av Office 365-trafik som, om routing via upptvingad tunnel-VPN och lokala nätverks kort, orsakar snabbt mättnad och kör VPN-infrastruktur utanför kapacitet. I den nya verkligheten är det inte längre att använda VPN för att få åtkomst till Office 365, utan en fast vägg som inte bara påverkar Office 365 men viktiga affärs åtgärder som fortfarande måste vara beroende av VPN för att fungera.

Microsoft har arbetat tätt med kunder och den större branschen under många år för att tillhandahålla effektiva, moderna lösningar till dessa problem i våra egna tjänster och för att justera med bransch metod tips. [Anslutnings principer](https://aka.ms/pnc) för Office 365-tjänsten har utformats för att fungera effektivt för fjärran vändare samtidigt som en organisation kan hantera säkerheten och kontrol lera anslutningen. De här lösningarna kan även implementeras snabbt med ett begränsat arbete som hittills har en betydande positiv inverkan på de problem som beskrivs ovan.

Microsofts rekommenderade strategi för att optimera fjärr anslutningens anslutnings barhet är att koncentrera dig på att snabbt minska problemen med den traditionella metoden och även ge dig höga prestanda med några enkla steg. De här stegen justerar den bakåtkompatibla VPN-inställningen för ett litet antal definierade slut punkter som kringgår virtuella nätverk med Flask hals. En motsvarande eller till en överlägsen säkerhets modell kan tillämpas på olika lager för att ta bort behovet att skydda all trafik när företagets nätverk tas ut. I de flesta fall kan detta uppnås inom några timmar och sedan begränsas till andra arbets belastningar efter behov och tid.

## <a name="common-vpn-scenarios"></a>Vanliga VPN-scenarier

I listan nedan ser du de vanligaste VPN-scenarier som visas i företags miljöer. De flesta kunder använder vanligt vis modell 1 (VPN-upptvingad tunnel). I det här avsnittet får du hjälp att snabbt och säkert övergå till **modell 2** , som kan nås med relativt lite ansträngning och har stora fördelar för nätverks prestanda och användar upplevelse.

| **Modell** | **Beskrivning** |
| --- | --- |
| [1. VPN-upptvingad tunnel](#1-vpn-forced-tunnel) | 100% av trafiken hamnar i VPN-tunnel, inklusive lokala, Internet och alla O365/M365 |
| [2. VPN upptvingad tunnel med få undantag](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN-tunnel används som standard (standard vägen till VPN), med några av de viktigaste undantagen som är tillåtna för att gå direkt |
| [3. VPN upptvingad tunnel med breda undantag](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN-tunnel används som standard (standard vägen till VPN), med breda undantag som får gå direkt (till exempel alla Office 365-alla Salesforce-funktioner) |
| [4. selektiv VPN-tunnel](#4-vpn-selective-tunnel) | VPN-tunnel används endast för Corpnet-baserade tjänster. Standard vägen (Internet och alla Internetbaserade tjänster) går direkt. |
| [5. inga VPN](#5-no-vpn) | En variant av #2 i stället för äldre VPN-tjänster publiceras genom moderna säkerhets åtgärder (som Zscaler ZPA, Azure Active Directory (Azure AD) proxy/MCAS, etc.) |

### <a name="1-vpn-forced-tunnel"></a>1. VPN-upptvingad tunnel

Det här är det vanligaste start scenariot för de flesta företags kunder. En tvingande VPN-anslutning används, vilket innebär att 100% av trafiken dirigeras till företags nätverket, oavsett slut punkten finns i företagets nätverk eller inte. Eventuell extern (Internet) bunden trafik, till exempel Office 365 eller Internet-surfning, hairpinned på lokal säkerhetsutrustning, till exempel proxyservrar. I det aktuella klimatet med nästan 100% av de användare som arbetar med fjärran sluts den modellen med en mycket hög belastning i VPN-infrastrukturen och den är sannolikt att avsevärt hindra all företags trafiks prestanda och därmed att företaget fungerar effektivt i ett kris läge.

![VPN-Användarkonfigurerad tunnel modell 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN-framtvingad tunnel med ett litet antal betrodda undantag

Den här modellen är betydligt mer effektiv för ett företag att fungera under eftersom den tillåter ett litet antal kontrollerade och definierade slut punkter som är mycket hög belastning och fördröjnings känsliga för att kringgå VPN-tunneln och gå direkt till Office 365-tjänsten i det här exemplet. Detta förbättrar prestanda i den avlastade tjänsten och minskar också belastningen på VPN-infrastrukturen, och därför kan det vara bra att använda element som fortfarande kräver att den fungerar med minskad innehålls påverkan för resurser. Det är den här modellen att den här artikeln koncentrerar sig på att hjälpa till med över gången så att den möjliggör enkla, definierade åtgärder som ska göras mycket snabbt med olika positiva resultat.

![VPN-modell för delade tunnlar 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN upptvingad tunnel med breda undantag

Den tredje modellen förlänger modellen två och inte bara skickar en liten grupp med definierade slut punkter direkt, men den skickar istället all trafik direkt till betrodda tjänster, till exempel Office 365 och SalesForce. Detta minskar belastningen på företagets VPN-infrastruktur och förbättrar tjänstens prestanda. Eftersom den här modellen troligen tar mer tid på att utvärdera genomförbarheten hos och implementera är det troligt vis ett steg som kan plockas iterativt vid ett senare tillfälle när modell två lyckas.

![Uppdelad tunnel VPN-modell 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. selektiv VPN-tunnel

Med den här modellen inverteras den tredje modellen för den trafik som identifieras som en företags-IP-adress, och därför skickas Internet-sökvägen till alla andra. Den här modellen kräver att en organisation är god på sökvägen till [noll](https://www.microsoft.com/security/zero-trust?rtc=1) för att det ska fungera säkert. Det bör noteras att denna modell eller vissa variationer blir troligt vis att det är nödvändigt att hålla med mer och mer än företags nätverket och till molnet. Microsoft använder den här modellen internt; du hittar mer information om Microsofts implementering av VPN-fildelning vid [körning på VPN: hur Microsoft sköter dess](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)fjärranställde.

![Uppdelad tunnel VPN-modell 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. inga VPN

En mer avancerad version av modell nummer två, där alla interna tjänster publiceras via en modern säkerhets metod eller SDWAN lösning, till exempel Azure AD proxy, MCAS, Zscaler ZPA, etc.

![Uppdelad tunnel-/VPN-Server](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>Implementera VPN-delning

I det här avsnittet hittar du de enkla stegen som krävs för att migrera din VPN-klients arkitektur från en _tvingande VPN-tunnel_ till en _VPN-Tvingad tunnel med ett mindre antal betrodda undantag_ , [VPN-delning av tunnel modell #2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) i avsnittet [common VPN-scenarier](#common-vpn-scenarios) .

I diagrammet nedan visas hur Rekommenderad VPN-delnings-tunnel-lösning fungerar:

![Information om delad tunnel-VPN-lösning](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. identifiera slut punkterna som ska optimeras

I avsnittet [Office 365 URL-adresser och IP-adressintervall](urls-and-ip-address-ranges.md) hittar Microsoft tydligt de viktigaste slut punkterna som du måste optimera och kategorisera dem som **optimera**. Det finns för närvarande bara fyra URL-adresser och tjugo IP-undernät som måste optimeras. Den här lilla gruppen slut punkter för cirka 70%-80% av volymen för trafik till Office 365-tjänsten, inklusive svars känsliga slut punkter, till exempel för grupp medier. Det här är den trafik som vi behöver för att under rättas om och är också den trafik som kommer att ge ett otrolig tryck på traditionella nätverks Sök vägar och VPN-infrastruktur.

URL-adresser i den här kategorin har följande egenskaper:

- Är Microsoft-ägda och hanterade slut punkter, som finns på Microsofts infrastruktur
- Har IP-adresser tillhandahålls
- Låg pris ändring och förväntas vara små i antal (för närvarande 20 IP-undernät)
- Är bandbredd och/eller fördröjnings känslig
- Kan ha nödvändiga säkerhets element i tjänsten i stället för på infogade nätverk
- Konto för omkring 70-80% av volymen för trafik till Office 365-tjänsten

Mer information om Office 365-slutpunkter och hur de kategoriseras och hanteras finns i artikeln [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md).

#### <a name="optimize-urls"></a>Optimera URL: er

Aktuella optimerade URL-adresser finns i tabellen nedan. Under de flesta omständigheter behöver du bara använda URL-slutpunkter i en [webbläsar-PAC-fil](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) där slut punkterna är konfigurerade att skickas direkt, i stället för till proxyservern.

| Optimera URL: er | Port/protokoll | Syfte |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Det här är en av de primära URL-adresser som Outlook använder för att ansluta till Exchange Online-servern och har en stor mängd bandbredds användning och antal anslutningar. Det krävs för lite nätverks fördröjning för online-funktioner, till exempel: snabb sökning, andra post lådans kalendrar, ledig/upptagen-uppslagning, hantera regler och aviseringar, Exchange Online-arkivering, e-post som avvecklar Utkorg |
| <https://outlook.office.com> | TCP 443 | Denna URL används för Outlook online Web Access för att ansluta till Exchange Online server och är känslig för nätverks fördröjning. Anslutningen är särskilt nödvändig för stor fil uppladdning och nedladdning med SharePoint Online. |
| https:// \<tenant\> . SharePoint.com | TCP 443 | Det här är den primära webb adressen för SharePoint Online och har hög bandbredds användning. |
| https:// \<tenant\> -My.SharePoint.com | TCP 443 | Det här är den primära URL-adressen för OneDrive för företag och har hög bandbredds användning och möjligt vis hög anslutnings räknare från OneDrive för företag-synkroniseringsklienten. |
| Teams Media-IP (ingen URL) | UDP 3478, 3479, 3480 och 3481 | Tilldelning av relä identifiering och real tids trafik (3478), ljud (3479), video (3480) och video skärm delning (3481). Dessa slut punkter används för Skype för företag och Microsoft Teams Media trafik (samtal, möten osv.). De flesta slut punkter tillhandahålls när Microsoft Teams-klienten upprättar ett samtal (och ingår i de IP-adresser som anges för tjänsten). Användning av UDP-protokollet krävs för optimal medie kvalitet.   |

I ovanstående exempel ska **klient organisationen** bytas ut mot Office 365-klientens namn. **Contoso.onmicrosoft.com** skulle till exempel använda _contoso.SharePoint.com_ och _constoso-My.SharePoint.com_.

#### <a name="optimize-ip-address-ranges"></a>Optimera IP-adressintervall

När du skriver de IP-intervall som dessa slut punkter motsvarar följer nedan. Vi **rekommenderar starkt** att du använder ett [skript som exempelvis det här](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) exemplet, [Office 365 IP-och URL-WEBBTJÄNST](microsoft-365-ip-web-service.md) eller [URL/IP-sida](urls-and-ip-address-ranges.md) för att kontrol lera eventuella uppdateringar när du tillämpar konfigurationen och ange en policy för att göra det regelbundet.

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

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. optimera åtkomst till dessa slut punkter via VPN

Nu när vi har identifierat dessa kritiska slut punkter måste vi omdirigera dem från VPN-tunneln och låta dem använda användarens lokala Internet anslutning för att ansluta direkt till tjänsten. Hur detta åstadkoms varierar beroende på vilken VPN-produkt och dator plattform som används, men de flesta VPN-lösningarna tillåter en del princip konfiguration för att tillämpa denna logik. Information om hur du får reda på mer om VPN-plattformar-specifika delnings tunnlar finns i [howto Guides](#howto-guides-for-common-vpn-platforms)

Om du vill testa lösningen manuellt kan du köra följande PowerShell-exempel för att emulera lösningen på väg tabell nivå. I det här exemplet läggs en väg till för var och en av gruppens medie-IP-undernät i väg tabellen. Du kan testa gruppens medie prestanda före och efter, och Observera skillnaden i flöden för angivna slut punkter.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Exempel: lägga till Teams Media-IP-undernät i väg tabellen

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

I ovanstående skript är _$intIndex_ indexet för det gränssnitt som är kopplat till Internet (hitta genom att köra **Skaffa-netadapter** i _PowerShell) och_ _$Gateway_ är standardgateway för det gränssnittet (hitta genom att köra **ipconfig** i en kommando tolk eller **(Get-NetIPConfiguration | IPv4DefaultGateway). NextHop** i PowerShell).

När du har lagt till vägarna kan du bekräfta att routningstabellen stämmer genom att köra **route print** i en kommando tolk eller PowerShell. Utdata ska innehålla de vägar som du lade till, med gränssnitts index ( _22_ i det här exemplet) och gatewayen för det gränssnittet ( _192.168.1.1_ i det här exemplet):

![Dirigera utskrifts utmatning](../media/vpn-split-tunneling/vpn-route-print.png)

Om du vill lägga till vägar för **alla** aktuella IP-adressintervall i optimerings kategorin kan du använda följande skript variation för att söka i [Office 365 IP-och URL-webbtjänsten](microsoft-365-ip-web-service.md) för den aktuella uppsättningen optimera IP-undernät och lägga till dem i väg tabellen.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Exempel: Lägg till alla optimera undernät i väg tabellen

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

Om du oavsiktligt lagt till vägar med felaktiga parametrar eller bara vill återställa dina ändringar kan du ta bort de vägar du just lagt till med följande kommando:

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

VPN-klienten bör konfigureras så att trafik till **optimerings** -IP-adresser routas på det här sättet. Detta gör att trafiken kan utnyttja lokala Microsoft-resurser, till exempel Office 365-tjänst front dörrar [, till exempel Azure-startdörren](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) som skickar Office 365-tjänster och anslutnings slut punkter så nära användarna som möjligt. Det gör det möjligt för oss att tillhandahålla extremt höga prestanda nivåer för användare var som helst i världen och utnyttjar [Microsofts globala världs klass globalt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/), vilket är mycket sannolikt inom ett litet antal millisekunder av dina användares direkta utgångar.

## <a name="configuring-and-securing-teams-media-traffic"></a>Konfigurera och skydda Teams Media trafik

Vissa administratörer kan kräva mer detaljerad information om hur samtals flöden fungerar i Teams med en delad tunnel modell och hur anslutningar skyddas.

### <a name="configuration"></a>Konfiguration

För både samtal och möten visas det lokala gränssnittet för Microsoft-destinationer i Microsofts IP-block ovan under förutsättning att de optimerade IP-näten för team medier fungerar korrekt i routningstabellen när Teams anropar funktionen [GetBestRoute](https://docs.microsoft.com/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) för att avgöra vilket gränssnitt som ska användas för en viss destination.

Vissa VPN-klientprogram tillåter cirkulations manipulering baserat på URL. Men det finns inga kopplade URL-adresser till gruppens medie trafik, så det är bara att kontrol lera routning för den här trafiken med hjälp av IP-undernät.

I vissa scenarier, som inte är relaterade till klient konfigurationen för team, passerar Media trafiken ändå VPN-tunneln även med rätt vägar på plats. Om du stöter på det här scenariot bör du använda en brand Väggs regel för att blockera teamens IP-undernät eller portar från att använda VPN.

>[!IMPORTANT]
>För att säkerställa att grupp medie trafiken routas med den önskade metoden i alla VPN-scenarier ska du se till att användarna kör Microsoft Teams- **1.3.00.13565** eller högre. Den här versionen inkluderar förbättringar av hur klienten identifierar tillgängliga nätverks Sök vägar.

Signal trafik utförs via HTTPS och är inte allt eftersom svars tiden är känslig för medie trafiken och är markerad som **Tillåt** i URL: en/IP-data och kan därför säkert dirigeras via VPN-klienten om så önskas.

### <a name="security"></a>Säkerhet

Ett vanligt argument för att undvika delade tunnlar är att det är mindre säkert att göra det, dvs. all trafik som inte går via VPN-tunneln kommer inte att dra fördel av vilket krypterings schema som används för VPN-tunneln och är därför mindre säkert.

Huvud räknare-argumentet-det här är att medie trafik redan har krypterats via _Secure Real-Time Transport Protocol (srtp)_ , en profil med Real-Time Transport Protocol (RTP) som tillhandahåller konfidentialitet, autentiseringsinformation och Replay-skydd till RTP-trafik. SRTP använder sig själv av en slumpmässigt genererad sessionsnyckel som utbyts via TLS-skyddad signal kanal. Det här är en bra detalj nivå i [den här säkerhets guiden](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online), men huvud delen av intresse är medie kryptering.

Media trafiken är krypterad med SRTP, som använder en sessionsnyckel som genereras av ett säkert slump tals Generator och utbyts med hjälp av TLS-kanalen för signaler. Dessutom krypteras inte medier med båda riktningarna mellan medlings servern och dess interna nästa hopp med SRTP.

Skype för företag – Online skapar användar namn/lösen ord för säker åtkomst till media reläs via en _genom gång med reläerna i stället för NAT (turn)_. Media vidarebefordrar användar namn och lösen ord via en TLS-skyddad SIP-kanal. Det är värt att Observera att även om en VPN-tunnel kan användas för att ansluta klienten till företags nätverket måste trafiken flöda i sin SRTP-form när den lämnar företags nätverket för att nå tjänsten.

Information om hur Teams minskar vanliga säkerhets problem, till exempel _verktyg för röst-och session Traversal för stun-attacker (-funktioner)_ [finns i den här artikeln](https://docs.microsoft.com/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c).

Du kan också läsa om moderna säkerhets kontroller i scenarion för fjärrarbetser på [alternativa sätt för säkerhets experter och för att få moderna säkerhets kontroller i dagens unika fjärr arbeten (Microsoft Security Team-bloggen)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

## <a name="testing"></a>Testning

När principen är på plats bör du bekräfta att den fungerar som den ska. Det finns flera sätt att testa sökvägen är korrekt inställd på att använda den lokala Internet anslutningen:

- Kör [Microsoft 365 Connectivity test](https://aka.ms/netonboard) som kör anslutnings test för dig, inklusive spårnings vägar som ovan. Vi lägger också till VPN-test i detta verktyg som också ska ge ytterligare insikter.

- En enkel tracert till en slut punkt i omfattningen av den delade tunneln ska visa sökvägen, till exempel:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  Du bör då se en sökväg via den lokala Internet leverantören till den här slut punkten som ska matcha en IP-adress i team områdena som vi har konfigurerat för att dela tunnlar.

- Ta en nätverks fångst med ett verktyg som Wireshark. Filtrera på UDP under ett samtal och se till att trafik flödar till en IP-adress i Teams **Optimize** Range. Om VPN-tunneln används för den här trafiken visas inte medie trafiken i spårningen.

### <a name="additional-support-logs"></a>Ytterligare support loggar

Om du behöver ytterligare data för att felsöka, eller om du vill få hjälp från Microsoft support, måste du skaffa följande information för att kunna hitta en lösning. Microsoft-supporten **TSS Windows cmd-baserad universell felsöka skript verktyg** kan hjälpa dig att samla in relevanta loggar på ett enkelt sätt. Verktyget och anvisningarna finns på <https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>HOWTO-handböcker för vanliga VPN-plattformar

Det här avsnittet innehåller länkar till detaljerade stöd linjer för att implementera delade tunnlar för Office 365-trafik från de vanligaste partners i det här rummet. Vi lägger till ytterligare stöd linjer när de blir tillgängliga.

- **Windows 10 VPN-klient** : [optimera Office 365-trafik för fjärranställda med den inbyggda Windows 10 VPN-klienten](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco AnyConnect** : [optimera AnyConnect dela tunnel för Office365](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo GlobalProtect** : [optimera Office 365-trafik via VPN delnings dirigering för delade tunnel](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5-nätverk stor-IP APM** : [optimera Office 365-trafik på fjärråtkomst via VPN när du använder stor-IP-APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix Gateway** : [optimerar Citrix Gateway VPN dela tunnel för Office365](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Puls säkra** : [VPN-tunnlar: Konfigurera delade tunnlar för att utesluta Office365-program](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **Kontrol lera Point VPN** : [Konfigurera delade tunnlar för Office 365 och andra SaaS-program](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>Vanliga frågor och svar

Microsoft-säkerhetsteamet har publicerat [en artikel](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) som beskriver viktiga sätt för säkerhets proffs och kan få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbetser. Dessutom är några vanliga kund frågor och svar på detta ämne.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Hur hindrar jag användare från att komma åt andra klient organisationer som jag inte litar på var de kan exfiltrate data?

Svaret är en [funktion som kallas innehavarens restriktioner](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions). Autentiseringstrafik är inte en hög volym eller särskilt Skift läges känslig så att den kan skickas via VPN-lösningen till den lokala proxyservern där funktionen används. En lista över tillåtna betrodda klient organisationer underhålls här och om klienten försöker erhålla en token till en klient organisation som inte är betrodd, nekar proxyservern helt enkelt begäran. Om klient organisationen är betrodd är en token tillgänglig om användaren har rätt behörighet.

Till och med om en användare kan göra en TCP/UDP-anslutning till den optimera markerade slut punkter ovan, utan giltig token för att få åtkomst till innehavaren i fråga, kan de inte loggas in och komma åt/flytta data.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Tillåter den här modellen åtkomst till konsument tjänster som privata OneDrive-konton?

Nej, det gör inte att Office 365-slutpunkter inte är samma som konsument tjänsterna (Onedrive.live.com som ett exempel) så att den delade tunneln inte tillåter att en användare får åtkomst direkt till konsument tjänster. Trafik till konsument slut punkter fortsätter att använda VPN-tunneln och befintliga principer fortsätter att tillämpas.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Hur använder jag DLP och skyddar mina känsliga data när trafiken inte längre flödar genom min lokala lösning?

Office 365 har många [inbyggda verktyg](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)för att förhindra oavsiktlig visning av känslig information. Du kan använda de inbyggda DLP- [funktionerna](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) i Teams och SharePoint för att upptäcka olämpligt lagrad eller delad känslig information. Om en del av din strategi för fjärr arbeten inbegriper en BYOD-princip (skaffa en person-egen enhet) kan du använda [app-baserad villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) för att förhindra att känslig information hämtas till användarnas personliga enheter

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Hur utvärderar och underhåller jag kontrollen för användarens verifikation när de ansluter direkt?

Utöver funktionen för klient begränsningar i Q1 kan [villkorsstyrda åtkomst principer](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) tillämpas för att dynamiskt bedöma risken för en autentiseringsbegäran och reagera på lämpligt sätt. Microsoft rekommenderar att du använder en policy för att [nollställa förtroendet](https://www.microsoft.com/security/zero-trust?rtc=1) över tiden och vi kan använda principer för villkorsstyrd åtkomst med Azure AD för att upprätthålla kontrollen i en mobil och ett moln först världen. Principer för villkorsstyrd åtkomst kan användas för att fatta ett real tids beslut om en autentiseringsbegäran lyckas baserat på olika faktorer som:

- Enhet, är enheten känd/Trusted/Domain ansluten?
- IP – är autentiseringsbegäran från en känd företags-IP-adress? Eller från ett land som vi inte litar på?
- Program – är den användare som har behörighet att använda det här programmet?

Vi kan sedan utlösa princip som Godkänn, utlösa MFA-eller blockera-verifikation baserat på dessa principer.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Hur skyddar jag mot virus och skadlig program vara?

Med Office 365 får du skydd för optimering av markerade slut punkter i olika lager i själva [tjänsten.](https://docs.microsoft.com/office365/Enterprise/office-365-malware-and-ransomware-protection) Som vi noterade är det mycket effektivare att tillhandahålla dessa säkerhets element i själva tjänsten i stället för att pröva och göra det i linje med enheter som kanske inte helt förstår protokoll/trafik. Standardinställningen är att SharePoint Online [automatiskt söker igenom fil överföringar](https://docs.microsoft.com/microsoft-365/security/office-365-security/virus-detection-in-spo) efter känt skadlig program vara

För Exchange [Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) och [Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) har du ett utmärkt jobb för att skydda trafiken till tjänsten.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Kan jag skicka mer än bara att optimera trafik direkt?

Prioritet bör ges för **optimering** av markerade slut punkter eftersom dessa ger maximal nytta för en nedsatt arbets nivå. Om du vill kan du använda Tillåt markerade slut punkter för att tjänsten ska fungera och ha IP-adresser för slut punkter som kan användas om så behövs.

Det finns också olika leverantörer som erbjuder molnbaserade proxy-eller säkerhetslösningar som kallas säkra webbgateways och som tillhandahåller Central säkerhet, kontroll-och företags principer. De här lösningarna fungerar bra i molnet i första världen, om de är mycket tillgängliga, utförda och etablerade nära användarna genom att tillåta säker Internet åtkomst från en molnbaserade plats nära användaren. Detta eliminerar behovet av en fäst via VPN/företags nätverket för allmän bläddring, samtidigt som den centrala säkerhets kontrollen fortfarande tillåts.

Även med dessa lösningar, rekommenderar Microsoft ändå att optimera markerade Office 365-trafik direkt till tjänsten.

Råd om hur du tillåter direkt åtkomst till ett virtuellt Azure-nätverk finns i artikeln [fjär arbete med Azure VPN gateway Point-to-Site](https://docs.microsoft.com/azure/vpn-gateway/work-remotely-support).

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Varför krävs port 80? Skickas trafiken i klartext?

Port 80 används bara för att till exempel omdirigera till en port 443-session, inga kunddata skickas eller kan nås via port 80. I [den här artikeln](https://docs.microsoft.com/microsoft-365/compliance/encryption) finns en översikt över kryptering av data i transit och på andra delar av Office 365, och [den här artikeln](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) beskriver hur vi använder srtp för att skydda Teams Media trafik.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>Gäller de här råden för användare i Kina med en världs omspännande instans av Office 365?

**Nej** , det gör det inte. Det enda villkoret för ovanstående råd är användare i Kina som ansluter till en världs omspännande instans av Office 365. På grund av den vanliga förekomsten av gränsöverskridande nätverks belastning i regionen kan direkt avlämning av Internet prestanda vara variabel. De flesta kunder i regionen samarbetar med ett VPN för att föra över trafiken till företagets nätverk och använda sin godkända MPLS-krets eller liknande att utlandet är på en optimerad väg. Detta beskrivs mer i artikeln [Office 365 Performance Optimization för Kina-användare](microsoft-365-networking-china.md).

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>Fungerar konfiguration för delade tunnlar för grupper som körs i en webbläsare?

**Nej** , det gör det inte. Den fungerar bara på klient versionen av Microsoft Teams-1.3.00.13565 eller senare. Den här versionen inkluderar förbättringar av hur klienten identifierar tillgängliga nätverks Sök vägar.

## <a name="related-topics"></a>Relaterade ämnen

[Översikt: dela VPN-tunnlar för Office 365](microsoft-365-vpn-split-tunnel.md)

[Office 365 prestanda optimering för Kina-användare](microsoft-365-networking-china.md)

[Alternativa sätt för säkerhetsexperter och för att få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbete (Microsoft Security Team-bloggen)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Förbättra VPN-prestanda på Microsoft: använda Windows 10-VPN-profiler för att tillåta anslutningar med automatisk anslutning](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Köra på VPN: hur Microsoft sköter fjärrarbets styrkan](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)

[Office 365 nätverks- och prestandajustering](network-planning-and-performance.md)
