---
title: Hantera Office 365-slutpunkter
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Lär dig hur du hanterar Office 365-slutpunkter så att de fungerar med företagets nätverks arkitektur.
ms.openlocfilehash: dcacb10492f4377dbcdf6e74c848a404f1b64c6f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780490"
---
# <a name="managing-office-365-endpoints"></a>Hantera Office 365-slutpunkter

De flesta företags organisationer som har flera Office-platser och anslutning till WAN kräver konfiguration för Office 365-nätverks anslutningar. Du kan optimera ditt nätverk genom att skicka alla betrodda Office 365-begäranden direkt via din brand vägg, och sedan gå förbi alla ytterligare paket nivå kontroller eller bearbetningar. Detta minskar svars tiden och dina krav på perimeter. Att identifiera nätverks trafik för Office 365 är det första steget med optimala prestanda för dina användare. Mer information finns i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).

Microsoft rekommenderar att du får till gång till Office 365 nätverks slut punkter och pågående ändringar i dem med hjälp av [IP-adressen och URL-adressen för office 365](microsoft-365-ip-web-service.md).

Oavsett hur du hanterar viktig Office 365-nätverks trafik kräver Office 365 Internet anslutning. Andra nätverks slut punkter där anslutning krävs visas i [ytterligare slut punkter som inte ingår i Office 365 IP Address and URL Web Service](additional-office365-ip-addresses-and-urls.md).

Hur du använder Office 365 nätverks slut punkter beror på företagets organisations nätverks arkitektur. I den här artikeln beskrivs flera olika sätt som företags nätverks arkitekturer kan integreras med Office 365 IP-adresser och URL: er. Det enklaste sättet att välja vilka nätverks förfrågningar som ska vara tillförlitliga är att använda SD-WAN-enheter som har stöd för automatisk Office 365-konfiguration på var och en av dina Office-platser.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD – WAN för lokal förgrening tillsluts av viktig Office 365-nätverks trafik

På varje filial kontors plats kan du tillhandahålla en SD-WAN-enhet som är konfigurerad för att cirkulera trafik för Office 365 optimerar kategorin med slut punkter eller optimerar och tillåter kategorier direkt till Microsofts nätverk. Annan nätverks trafik inklusive lokal data Center trafik, allmän trafik på Internet webbplatser och trafik till Office 365 standard kategori slut punkter skickas till en annan plats där du har en större nätverks gräns.

Microsoft arbetar med SD-WAN-leverantörer för att aktivera automatisk konfiguration. Mer information finns i [Office 365 Network partner program](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Använda en PAC-fil för direkt dirigering av viktig Office 365-trafik

Använd PAC-eller WPAD-filer för att hantera nätverks förfrågningar som är kopplade till Office 365 men inte har någon IP-adress. Vanliga nätverks begär Anden som skickas via en proxy eller en perimeter-enhet. Medan SSL Avbryt och inspektera skapar den största fördröjningen kan andra tjänster, till exempel proxyautentisering och ryktes uppslag, orsaka dålig prestanda och dåligt användar upplevelse. Dessutom behöver de här perimeternätverket tillräckligt med kapacitet för att bearbeta alla nätverks anslutnings förfrågningar. Vi rekommenderar att du kringgår dina proxy-eller kontroll enheter för direkta Office 365-begäranden.
  
[PowerShell-galleriet get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) är ett PowerShell-skript som läser de senaste nätverks slut punkterna från Office 365 IP Address and URL web service och skapar ett exempel på en PAC-fil. Du kan ändra skriptet så att det integreras med din befintliga PAC-filhantering.

![Ansluter till Office 365 via brand väggar och proxyservrar.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Bild 1 – enkel perimeter för företags nätverk**

PAC-filen distribueras till webbläsare vid punkt 1 i bild 1. När du använder en PAC-fil för direkt utlämnande av viktig Office 365-nätverks trafik måste du även tillåta anslutning till IP-adresserna bakom dessa URL-adresser i nätverks gräns brand väggen. Detta görs genom att hämta IP-adresserna för samma Office 365-slutpunkts kategorier enligt PAC-filen och skapa brand Väggs åtkomst kontrol listor baserat på dessa adresser. Brand väggen är punkt 3 i bild 1.

Separat om du väljer att göra en direkt dirigering för optimerings kategorins slut punkter måste alla tillåtna slut punkter för varje kategori som du skickar till proxyservern finnas med i proxyservern för att det ska gå vidare. SSL-avbrott och inspektion och proxyautentisering är till exempel inkompatibla med både optimerings-och tillåtna kategori slut punkter. Proxyservern är punkt 2 i bild 1.

Den gemensamma konfigurationen är att tillåta utan att bearbeta all utgående trafik från proxyservern för mål-IP-adresser för Office 365 nätverks trafik som ger proxyservern. Information om problem med SSL-avbrott och inspektion finns i [använda nätverks enheter eller-lösningar från tredje part i Office 365-trafik](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Det finns två typer av PAC-filer som Get-PacFile-skriptet skapar.

| Type (Typ) | Beskrivning |
|:-----|:-----|
|**9.1** <br/> |Skicka optimering av slut punkts trafik direkt och allt annat till proxyservern. <br/> |
|**två** <br/> |Skicka optimering och Tillåt slut punkts trafik direkt och allt annat till proxyservern. Den här typen kan också användas för att skicka alla ExpressRoute som stöds för Office 365-trafik till ExpressRoute nätverks segment och allt annat till proxyservern. <br/> |

Här är ett enkelt exempel på hur du anropar PowerShell-skriptet:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Det finns många parametrar som du kan skicka till skriptet:

| Indataparametern | Beskrivning |
|:-----|:-----|
|**ClientRequestId** <br/> |Det här är obligatoriskt och är en GUID som skickas till webb tjänsten som representerar den klient dator som ringer samtalet. <br/> |
|**Enhetsinstans** <br/> |Office 365-tjänst instans som är som standard världen över. Detta skickas också till webb tjänsten. <br/> |
|**TenantName** <br/> |Ditt Office 365-klient namn. Skickades till webb tjänsten och används som en återställnings bara parameter i vissa Office 365-URL: er. <br/> |
|**Typ** <br/> |Den typ av PAC som du vill skapa. <br/> |

Här är ett annat exempel på hur du anropar PowerShell-skriptet med ytterligare parametrar:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Kringgå behandling av nätverks trafik för Office 365 i proxyservern

Där PAC-filer inte används för direkt utgående trafik, vill du ändå kringgå bearbetningen av nätverks omkretsen genom att konfigurera proxyservern. Vissa proxyservrar har aktiverat automatisk konfiguration av detta enligt beskrivningen i [Office 365 Network partner-programmet](microsoft-365-networking-partner-program.md).

Om du gör detta manuellt måste du skaffa optimerings-och tillåtna slut punkts kategori data från Office 365 IP Address and URL web service och konfigurera din proxyserver för att kringgå bearbetningen för dessa. Det är viktigt att undvika SSL-avbrott och inspektera och proxyautentisering för optimerings-och grupp slut punkter.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Ändrings hantering för Office 365 IP-adresser och URL: er

Förutom att välja rätt konfiguration för nätverks omkretsen är det viktigt att du använder en process för ändrings hantering för Office 365-slutpunkter. Dessa slut punkter ändras regelbundet och om du inte hanterar ändringarna kan du avsluta med blockerade användare eller dåliga prestanda efter en ny IP-adress eller URL.

Ändringar av IP-adresser och URL: er för Office 365 publiceras vanligt vis nära den sista dagen i varje månad. Ibland kommer en ändring att publiceras utanför detta schema på grund av drift-, support-eller säkerhets krav.

Om en ändring publiceras som kräver att du har lagt till en IP-adress eller URL-adress, bör du förvänta dig 30 dagars varsel från den tidpunkt då vi publicerar ändringen tills det finns en Office 365-tjänst på den slut punkten. Även om vi strävar efter att visa denna meddelande period kanske det inte alltid är möjligt på grund av drift-, support-och säkerhets krav. Ändringar som inte kräver någon omedelbar åtgärd för att upprätthålla anslutningen, till exempel borttagna IP-adresser och URL-adresser eller mindre väsentliga ändringar, inkluderar inte förhands avisering. Oberoende av vilken avisering som tillhandahålls visar vi den förväntade tjänstens aktiva datum för varje ändring.

### <a name="change-notification-using-the-web-service"></a>Ändrings meddelande med webb tjänsten

Du kan använda Office 365 IP Address and URL Web Service för att få ett meddelande om ändring. Vi rekommenderar att du ringer till **/version** webb metod en gång i timmen för att kontrol lera den version av slut punkterna som du använder för att ansluta till Office 365. Om den här versionen ändras när den jämförs med den version som du har använt, bör du skaffa de senaste slut punkts uppgifterna från webb metoden **/endpoints** och även använda de skillnader som råder från **/Changes** webb metod. Det är inte nödvändigt att ringa webb metoderna **/endpoints** eller **/Changes** om ingen ändring har gjorts för den version du hittade.

Mer information finns i [Office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Ändra meddelande med RSS-feeds

Webb adressen och URL-webbtjänsten för Office 365 tillhandahåller en RSS-feed som du kan abonnera på i Outlook. Det finns länkar till RSS-webbadresserna på var och en av de särskilda sidorna för Office 365-tjänsterna för IP-adresser och URL: er. Mer information finns i [Office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Ändring av meddelanden och godkännande granskning med Microsoft-flöde

Vi förstår att du fortfarande kan behöva manuell bearbetning för ändringar av nätverks slut punkter i varje månad. Du kan använda Microsoft Flow för att skapa ett flöde som meddelar dig via e-post och som om en godkännande process körs för ändringar när Office 365-nätverks slut punkter har ändrats. När granskningen är klar kan du låta flödesschemat Skicka automatiskt e-poständringarna till din brand vägg och server för hanterings servrar.

Information om ett Microsoft-flödes exempel och-mall finns i [använda Microsoft Flow för att få ett e-postmeddelande för ändringar i Office 365 IP-adresser och URL: er](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651).
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Vanliga frågor om Office 365-nätverks slut punkter

Se de här vanliga frågorna om Office 365-nätverks anslutningar.
  
### <a name="how-do-i-submit-a-question"></a>Hur skickar jag in en fråga?

Klicka på länken längst ned för att visa om artikeln var till hjälp eller inte och skicka eventuella ytterligare frågor. Vi övervakar feedbacken och uppdaterar frågorna här med de vanligaste frågorna.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Hur avgör jag platsen för min klient organisation?

 **Klient platsen** bestäms bäst med hjälp av vår [Data Center karta](https://aka.ms/datamaps).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Är jag peer-lämpligt med Microsoft?

 **Peering-platser** beskrivs mer ingående i [peering med Microsoft](https://www.microsoft.com/peering).
  
Med över 2500 ISP-relationer globalt och 70 punkter i närvaro bör du komma från ditt nätverk till vår är sömlöst. Det går inte göra illa att ta några minuter att se till att din Internet leverantörs peer-relation är den mest optimala, [här är några exempel](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) på bra och inte så bra bearbetande med dina nätverk.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Jag ser nätverks förfrågningar till IP-adresser som inte finns på den publicerade listan, jag behöver ge åtkomst till dem?

Vi tillhandahåller bara IP-adresser för de Office 365-servrar som du ska dirigera direkt till. Det här är inte en fullständig lista över alla IP-adresser som du ser nätverks förfrågningar för. Du kommer att se nätverks förfrågningar till Microsoft och ägda, opublicerade och IP-adresser från tredje part. Dessa IP-adresser skapas eller hanteras dynamiskt på ett sätt som gör att du inte kan se tid när de ändrar. Om din brand vägg inte kan tillåta åtkomst baserat på FQDN-namn för dessa nätverks förfrågningar använder du en PAC-eller WPAD-fil för att hantera begär Anden.
  
Finns det en IP-adress som är kopplad till Office 365 som du vill ha mer information om?
  
1. Kontrol lera att IP-adressen ingår i ett större publicerat område med hjälp av en CIDR-kalkylator, till exempel [IPv4](https://www.ipaddressguide.com/cidr) eller [IPv6](https://www.ipaddressguide.com/ipv6-cidr). 40.96.0.0/13 inkluderar till exempel IP-adressen 40.103.0.1 trots att 40,96 inte matchar 40,103.
2. Se om en partner äger IP-adressen med en [whois-fråga](https://dnsquery.org/). Om det ägs av Microsoft kan det vara en intern partner. Många slut punkter för partner nätverk visas som tillhör _standard_ kategorin, för vilka IP-adresser inte är publicerade.
3. IP-adressen får inte vara en del av Office 365 eller ett samband. Nätverks slut punkter för Office 365 inkluderar inte alla slut punkter för Microsoft-nätverk.
4. Kontrol lera certifikatet. Med en webbläsare ansluter du till den IP-adress som använder *https:// \<IP_ADDRESS\>* och kontrollerar vilka domäner som är kopplade till IP-adressen genom att markera domänerna i certifikatet. Om det är en Microsoft-adress och inte i listan med IP-adresser för Office 365 är det troligt vis IP-adressen som är kopplad till ett Microsoft CDN, till exempel  *MSOCDN.net*  eller en annan Microsoft-domän utan offentlig IP-information. Om du hittar domänen på certifikatet är ett ställe där vi hävdar att det finns en lista med IP-adressen ber vi dig berätta.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Vissa Office 365-adresser pekar på CNAME-poster i stället för en post i DNS. Vad måste jag göra med CNAME-posterna?

Klient datorer behöver en DNS A-eller AAAA Record t)-hatt inkluderar en eller flera IP-adresser att ansluta till en moln tjänst. Vissa URL-adresser i Office 365 visar CNAME-poster i stället för A-eller AAAA-poster. Dessa CNAME-poster är mellanhand och det kan finnas flera i en kedja. De kommer alltid att behöva komma till en A-eller AAAA-post för en IP-adress. Överväg till exempel följande serie av DNS-poster, som i slut ända till IP-adressen _IP_1_:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Dessa CNAME-omdirigeringar är en normal del av DNS och är transparenta för klient datorn och är transparent för proxyservrar. De används för belastnings utjämning, innehålls leverans nätverk, hög tillgänglighet och minskning av service händelser. Microsoft publicerar inte de mellanliggande CNAME-posterna, de kan ändras när som helst och du bör inte behöva konfigurera dem som tillåtna i din proxyserver.

En proxyserver verifierar den inledande URL-adressen, som i exemplet ovan är serviceA.office.com och denna URL inkluderas i Office 365-publiceringen. Proxyservern begär DNS-matchning av URL-adressen till en IP-adress och får tillbaka IP_1. Det verifierar inte de mellanliggande CNAME-omdirigerings posterna.

Hårdkodade konfigurationer eller att tillåta trafik baserat på indirekta Office 365 FQDN-namn rekommenderas inte, stöds inte av Microsoft och är känd för att orsaka problem med kund anslutningen. DNS-lösningar som blockerar CNAME-omdirigering eller som annars löser Office 365 DNS-poster kan lösas genom villkorlig DNS-vidarebefordran (omfattning för direkt använda Office 365 FQDN) med DNS rekursion aktiverat. Många nätverks gräns produkter från tredje part integrerar den rekommenderade Office 365-slutlinjens konfiguration med hjälp av [IP-adressen och URL-adressen för office 365](microsoft-365-ip-web-service.md).

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Varför ser jag namn som nsatc.net eller akadns.net i domän namnen för Microsoft?

Office 365 och andra Microsoft-tjänster använder flera tredjepartsprogram som Akamai och MarkMonitor för att förbättra din Office 365-upplevelse. För att det ska bli så bra som möjligt kan vi ändra dessa tjänster i framtiden. Tredjeparts domäner kan hantera innehåll, till exempel en CDN, eller de kan vara värd för en tjänst, till exempel en tjänst för en geografisk trafik. Här är några av de tjänster som används för närvarande:
  
[MarkMonitor](https://www.markmonitor.com/) används när du ser förfrågningar som innehåller *\* . nsatc.net*. Denna tjänst tillhandahåller domän namns skydd och övervakning för att skydda mot skadligt beteende.
  
[ExactTarget](https://www.marketingcloud.com/) används när du ser förfrågningar till *\* . ExactTarget.com*. Den här tjänsten tillhandahåller hantering av e-postlänk och övervakning mot skadligt beteende.
  
[Akamai](https://www.akamai.com/) används när du ser förfrågningar som innehåller något av följande FQDN-namn. Den här tjänsten erbjuder nätverks tjänster för geo-DNS och innehålls leverans.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Jag måste ha den minsta möjliga anslutningen för Office 365

Eftersom Office 365 är en uppsättning tjänster som är byggda för att fungera över Internet, baseras tillförlitlighet och tillgänglighet på många vanliga Internet-tjänster. Vanliga Internet-tjänster, till exempel DNS, CRL och CDN, måste kunna nås för att kunna använda Office 365 på samma sätt som de måste kunna använda för de flesta moderna Internet-tjänster.

Office 365-sviten är uppdelad i huvud tjänst områden. Dessa kan vara selektivt aktiverade för anslutning och det finns ett gemensamt område, vilket är ett samband för alla och som alltid är obligatoriskt.

| Tjänst område | Beskrivning |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online och Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online och OneDrive för företag <br/> |
|**Skype för företag Online och Microsoft Teams** <br/> |Skype för företag och Microsoft Teams <br/> |
|**Gemenskapens** <br/> |Office 365 Pro Plus, Office i en webbläsare, Azure AD och andra vanliga nätverks slut punkter <br/> |

Utöver de grundläggande Internet-tjänsterna finns det tjänster som bara används för att integrera funktionalitet. Medan dessa behövs för integrering är de markerade som valfria i avsnittet Office 365-slutpunkter, vilket innebär att de grundläggande funktionerna i tjänsten fortsätter att fungera om slut punkten inte är tillgänglig. Alla nätverks slut punkter som krävs kommer att ha attributet obligatoriskt angivet till true. Alla nätverks slut punkter som är valfria kommer att ha attributet #a0 inställt på falskt och attributet Obs! visar de saknade funktioner som du bör förvänta dig om anslutningen blockeras.
  
Om du försöker använda Office 365 och letar efter tjänster från tredje part är inte tillgängliga, bör du [kontrol lera att alla FQDN-namn är markerade som obligatoriska eller valfria i den här artikeln tillåts via proxyn och brand väggen](urls-and-ip-address-ranges.md).
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Hur blockerar jag åtkomst till Microsofts konsument tjänster?

Att begränsa åtkomsten till våra konsument tjänster bör göras på egen risk. Det enda säkra sättet att blockera konsument tjänster är att begränsa åtkomsten till FQDN för  *login.live.com*  . Detta FQDN används av en mängd olika tjänster, inklusive tjänster som inte är konsumenter, till exempel MSDN, TechNet och andra. Detta FQDN används också av Microsoft-Supportens säkra fil utbytes program och det är nödvändigt att överföra filer för att under lätta fel sökning av Microsoft-produkter.  Om du begränsar åtkomsten till detta FQDN kan det leda till att du även inkluderar undantag från regeln för nätverks förfrågningar som är associerade med dessa tjänster.
  
Tänk på att du inte kan förhindra att någon i nätverket kan exfiltrate information med hjälp av en Office 365-klient organisation eller annan tjänst.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Brand väggen kräver IP-adresser och kan inte hantera URL: er. Hur konfigurerar jag det för Office 365?

Office 365 tillhandahåller inte IP-adresser till alla nödvändiga nätverks slut punkter. Vissa tillhandahålls endast som URL-adresser och kategoriseras som standard. URL-adresser i Standard kategorin som behövs bör tillåtas via en proxyserver. Om du inte har någon proxyserver kan du läsa om hur du har konfigurerat webbegäranden för webb adresser som användare skriver i adress fältet i en webbläsare. användaren anger ingen IP-adress. URL-adresserna för Office 365 som inte tillhandahåller IP-adresser bör konfigureras på samma sätt.

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Microsoft Azure Datacenter IP-intervall](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Krav för nätverks infrastruktur för Microsoft Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute och Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)
  
[Hantera ExpressRoute för Office 365](managing-expressroute-for-connectivity.md)
  
[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)
