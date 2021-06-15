---
title: Hantera Office 365-slutpunkter
ms.author: kvice
author: kelleyvice-msft
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
description: Lär dig hur du Office 365 av slutpunkter så att de fungerar med företagets nätverksarkitektur.
ms.openlocfilehash: fa727c5c80521b6ff67c50d202d0c11c643b021e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925869"
---
# <a name="managing-office-365-endpoints"></a>Hantera Office 365-slutpunkter

De flesta företag som har flera kontorsplatser och ett anslutande WAN måste konfigureras för Office 365 nätverksanslutningar. Du kan optimera nätverket genom att skicka alla betrodda Office 365-nätverksbegäranden direkt genom brandväggen, eller genom att hoppa över all ytterligare kontroll eller behandling på paketnivån. Detta minskar svarstiden och kraven på perimeterkapacitet. Att Office 365 att identifiera nätverkstrafik är det första steget för att ge användarna optimala prestanda. Mer information finns i Office 365 [principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

Microsoft rekommenderar att du använder Office 365 och kontinuerliga ändringar av dem med hjälp av IP Office 365- och [URL-webbtjänsten](microsoft-365-ip-web-service.md)för Office 365.

Oavsett hur du hanterar viktig Office 365 nätverkstrafik krävs Office 365 Internetanslutning. Andra nätverksslutpunkter där anslutning krävs finns med i Ytterligare slutpunkter som inte [ingår Office 365 IP-adress och URL-webbtjänst.](additional-office365-ip-addresses-and-urls.md)

Hur du använder Office 365 nätverksslutpunkter beror på företagets nätverksarkitektur. I den här artikeln beskrivs flera sätt som företagsnätverksarkitekturer kan integrera med IP Office 365 adresser och URL:er. Det enklaste sättet att välja vilka nätverksbegäranden att lita på är att använda SD-WAN-enheter som stöder automatiserad Office 365 konfiguration på var och en av dina kontorsplatser.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD-WAN för lokal grenens utgående viktiga Office 365 nätverkstrafik

På varje filialplats kan du ange en SD-WAN-enhet som är konfigurerad för att dirigera trafik för Office 365 optimera kategori av slutpunkter, eller kategorierna Optimera och tillåt, direkt till Microsofts nätverk. Annan nätverkstrafik, inklusive lokal datacentertrafik, allmän internetwebbplatstrafik och trafik till Office 365 Standardkategorislutpunkter skickas till en annan plats där du har en mer avsevärd nätverks perimeter.

Microsoft arbetar med SD-WAN-leverantörer för att möjliggöra automatiserad konfiguration. Mer information finns i [Office 365 Nätverkspartnerprogram](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Använda en PAC-fil för direkt dirigering av viktig Office 365 trafik

Använd PAC- eller WPAD-filer för att hantera nätverksbegäranden som är Office 365 men som inte har någon IP-adress. Typiska nätverksbegäranden som skickas genom en proxy eller perimeterenhet ökar svarstiden. Ssl-avbrott och -inspektera skapar den största svarstiden, men andra tjänster som proxyautentisering och ryktesuppslag kan orsaka dålig prestanda och en dålig användarupplevelse. De här perimeternätverksenheterna behöver dessutom tillräckligt med kapacitet för att bearbeta alla förfrågningar om nätverksanslutning. Vi rekommenderar att du kringgår din proxy- eller kontrollenheter för Office 365 nätverksbegäranden.
  
[PowerShell-galleriet Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) är ett PowerShell-skript som läser upp de senaste nätverksslutpunkterna från IP-tjänsten Office 365 och URL-webbtjänsten och skapar ett exempel på EN PAC-fil. Du kan ändra skriptet så att det integreras med din befintliga PAC-filhantering.

![Ansluter till Office 365 genom brandväggar och proxy.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Bild 1 – Enkel företagsnätverks perimeter**

PAC-filen distribueras till webbläsare vid punkt 1 i Bild 1. När du använder en PAC-fil för direkt utgående viktig Office 365-nätverkstrafik måste du också tillåta anslutning till IP-adresserna bakom dessa URL:er på nätverkets perimeterbrandvägg. Det görs genom att hämta IP-adresser för samma Office 365 ändpunktskategorier som anges i PAC-filen och skapa brandväggs-ACL:er baserat på de adresserna. Brandväggen är punkt 3 i Bild 1.

Separat om du väljer att endast göra direktdirigering för slutpunkter för optimera kategori, måste alla obligatoriska slutpunkter för tillåt kategori som du skickar till proxyservern listas i proxyservern för att kringgå ytterligare bearbetning. Till exempel är SSL-avbrott och kontrollerad proxyautentisering inte kompatibla med både slutpunkter för optimera och tillåt. Proxyservern är punkt 2 i bild 1.

Den vanliga konfigurationen är att tillåta utan att bearbeta all utgående trafik från proxyservern för mål-IP-adresserna för Office 365-nätverkstrafik som träffar proxyservern. Mer information om problem med SSL-avbrott och -inspektera finns i [Använda nätverksenheter eller lösningar från tredje Office 365 trafik.](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)

Det finns två typer av PAC-filer som Get-PacFile skapar.

| Typ | Beskrivning |
|:-----|:-----|
|**1** <br/> |Skicka trafik från slutpunktstrafiken Optimera och allt annat till proxyservern. <br/> |
|**2** <br/> |Skicka optimera och tillåt slutpunktstrafik direkt och allt annat till proxyservern. Den här typen kan även användas för att skicka all ExpressRoute som stöds för Office 365 till ExpressRoute-nätverkssegment och allt annat till proxyservern. <br/> |

Här är ett enkelt exempel på hur du anropar PowerShell-skriptet:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Det finns många parametrar som du kan överföra till skriptet:

| Parameter | Beskrivning |
|:-----|:-----|
|**ClientRequestId** <br/> |Detta är obligatoriskt och är ett GUID som skickas till webbtjänsten som representerar den klientdator som ringer samtalet. <br/> |
|**Instans** <br/> |Den Office 365 tjänstinstans, som är den globala standardinställningen. Det här skickas också till webbtjänsten. <br/> |
|**TenantName** <br/> |Namnet Office 365 klientorganisationen. Skickas till webbtjänsten och används som en ersättbar parameter i vissa Office 365 URL:er. <br/> |
|**Typ** <br/> |Den typ av proxy-PAC-fil som du vill generera. <br/> |

Här är ett annat exempel på hur du anropar PowerShell-skriptet med ytterligare parametrar:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Proxyserverförkoppling av Office 365 nätverkstrafik

Om PAC-filer inte används för direkt utgående trafik vill du fortfarande kringgå bearbetningen på nätverkets perimeter genom att konfigurera din proxyserver. Vissa proxyserverleverantörer har aktiverat automatisk konfiguration av detta enligt beskrivningen i [Office 365 Nätverkspartnerprogram](microsoft-365-networking-partner-program.md).

Om du gör det manuellt måste du hämta kategoridata för optimera och tillåt slutpunkt från ip-tjänsten Office 365-adress och URL samt konfigurera din proxyserver för att kringgå bearbetning för dessa. Det är viktigt att undvika SSL-avbrott och kontrollera och proxyautentisering för kategorislutpunkterna optimera och tillåt.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Ändringshantering för Office 365 IP-adresser och URL:er

Förutom att välja lämplig konfiguration för nätverks perimeter är det viktigt att du inför en ändringshanteringsprocess för Office 365 slutpunkter. Dessa slutpunkter ändras regelbundet och om du inte hanterar ändringarna kan du få användare blockerade eller med dålig prestanda när en ny IP-adress eller URL läggs till.

Ändringar av IP Office 365 och URL-adresser publiceras vanligtvis nära den sista dagen i varje månad. Ibland publiceras en ändring utanför schemat på grund av driftkrav, support eller säkerhetskrav.

När en ändring publiceras som kräver att du agerar eftersom en IP-adress eller URL lades till, bör du få 30 dagars förvarning från den tidpunkt då vi publicerar ändringen tills det finns en Office 365-tjänst på den slutpunkten. Även om vi siktar på den här aviseringsperioden kanske det inte alltid är möjligt på grund av drift, support eller säkerhetskrav. Ändringar som inte kräver omedelbar åtgärd för att upprätthålla anslutningen, t.ex. borttagna IP-adresser eller URL-adresser eller mindre betydande ändringar, inkluderar inte förhandsmeddelande. Oavsett vilket meddelande som tillhandahålls visas det förväntade aktiva tjänstdatumet för varje ändring.

### <a name="change-notification-using-the-web-service"></a>Ändra meddelande med webbtjänsten

Du kan få ändringsmeddelande Office 365 använda IP-adress och URL-webbtjänst. Vi rekommenderar att du ringer **versionswebbmetoden** en gång i timmen och kontrollerar vilken version av slutpunkterna som du använder för att ansluta till Office 365. Om den här versionen ändras jämfört med den version som du använder bör du hämta de senaste slutpunktsdata från **/endpoints-webbmetoden** och, om du vill, skillnaderna från **/changes-webbmetoden.** Du behöver inte anropa **/endpoints eller** **/changes-webbmetoder** om det inte har skett någon ändring i versionen du hittade.

Mer information finns i Office 365 [IP-adress och URL-webbtjänst.](microsoft-365-ip-web-service.md)

### <a name="change-notification-using-rss-feeds"></a>Ändra aviseringar med RSS-feeds

I ip Office 365 adress- och URL-webbtjänsten får du en RSS-feed som du kan prenumerera på Outlook. Det finns länkar till RSS-URL:er på var och en Office 365 instansspecifika sidor för IP-adresser och URL:er. Mer information finns i Office 365 [IP-adress och URL-webbtjänst.](microsoft-365-ip-web-service.md)

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Ändra meddelande och granskning av godkännande med Microsoft Flow

Vi förstår att du kanske fortfarande behöver manuell bearbetning för ändringar av nätverksslutpunkt som kommer igenom varje månad. Du kan använda Microsoft Flow för att skapa ett flöde som meddelar dig via e-post och eventuellt kör en godkännandeprocess för ändringar när Office 365 nätverksslutpunkter har ändringar. När granskningen är klar kan du få flödet att automatiskt skicka ändringar av brandväggen och proxyserverhanteringsteamet via e-post.

Mer information om en Microsoft Flow exempel och mall finns i Använda Microsoft Flow för att ta emot ett e-postmeddelande för [ändringar Office 365 IP-adresser och URL:er.](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651)
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Office 365 vanliga frågor och svar om nätverksslutpunkter

Se de här vanliga frågorna om Office 365 nätverksanslutningen.
  
### <a name="how-do-i-submit-a-question"></a>Hur skickar jag in en fråga?

Klicka på länken längst ned för att ange om artikeln var användbar eller inte, och skicka in ytterligare frågor. Vi övervakar den feedback vi får och uppdaterar med de vanligaste frågorna här.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Hur tar jag reda på platsen för min klientorganisation?

 **Klientorganisationens** plats avgörs bäst med hjälp av [vår datacenterkarta](./o365-data-locations.md).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Är min peering med Microsoft korrekt?

 **Peeringplatser beskrivs** mer ingående i [peering med Microsoft](https://www.microsoft.com/peering).
  
Med över 2 500 peeringrelationer mellan Internet och 70 närvaropunkter ska det vara smidigt att få från ditt nätverk till vårt. Det kan vara svårt att ägna några minuter åt att se till att din Internetleverantörs peeringrelation är den mest [optimala,](/archive/blogs/onthewire/__guidance) här är några exempel på bra och inte så bra peering-peering till vårt nätverk.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Jag ser nätverksförfrågningar till IP-adresser som inte finns med på den publicerade listan, behöver jag ge åtkomst till dem?

Vi anger endast IP-adresser för de Office 365 som du ska dirigera direkt till. Det här är inte en fullständig lista över alla IP-adresser som du kommer att få se nätverksbegäranden för. Du kommer att se nätverksbegäranden till Microsoft och opublicerade IP-adresser som ägs av tredje part. Dessa IP-adresser genereras dynamiskt eller hanteras på ett sätt som gör att det inte går att få ett meddelande i tid när de ändras. Om din brandvägg inte tillåter åtkomst baserat på FQDN för dessa nätverksbegäranden använder du en PAC- eller WPAD-fil för att hantera begärandena.
  
Ser du en IP som är Office 365 adress som du vill ha mer information om?
  
1. Kontrollera om IP-adressen ingår i ett större publicerat område med en CIDR-miniräknare, till exempel dessa för [IPv4](https://www.ipaddressguide.com/cidr) eller [IPv6.](https://www.ipaddressguide.com/ipv6-cidr) Exempel: 40.96.0.0/13 inkluderar IP-adressen 40.103.0.1 trots att 40,96 inte matchar 40,103.
2. Se om en partner äger IP-adressen med en [whois-fråga](https://dnsquery.org/). Om det ägs av Microsoft kan det vara en intern partner. Många slutpunkter för partnernätverk anges som tillhör _standardkategorin,_ för vilka IP-adresser inte publiceras.
3. IP-adressen kanske inte är en del Office 365 eller ett beroende. Office 365-nätverksslutpunktspublicering inkluderar inte alla Microsoft-nätverksslutpunkter.
4. Kontrollera certifikatet. Med en webbläsare ansluter du till IP-adressen med *hjälp HTTPS:// \<IP_ADDRESS\>* och kontrollerar domänerna som visas på certifikatet för att förstå vilka domäner som är kopplade till IP-adressen. Om det är en IP-adress som ägs av Microsoft och inte finns med i listan över Office 365 IP-adresser är det troligt att IP-adressen är kopplad till ett Microsoft CDN som *MSOCDN.NET* eller en annan Microsoft-domän utan publicerad IP-information. Om du hittar domänen på certifikatet är en där vi gör anspråk på att ange IP-adressen, berätta det för oss.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Vissa Office 365 URL:er pekar på CNAME-poster i stället för A-poster i DNS. Vad har jag att göra med CNAME-posterna?

Klientdatorer behöver en DNS A- eller AAAA-post t)hat innehåller en eller flera IP-adresser för att ansluta till en molntjänst. Vissa URL:er som ingår i Office 365 CNAME-poster visas i stället för A- eller AAAA-poster. Dessa CNAME-poster är mellanled och det kan finnas flera i en kedja. De löser alltid så småningom A- eller AAAA-posten för en IP-adress. Tänk dig exempelvis följande serie DNS-poster, som i slutänden matchas till _IP-IP_1:_

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Dessa CNAME-omdirigeringar är en normal del av DNS-posterna och är transparenta mot klientdatorn och transparenta mot proxyservrar. De används för belastningsutjämning, nätverk för innehållsleverans, hög tillgänglighet och åtgärder för incidentåtgärder. Microsoft publicerar inte CNAME-mellanledande poster, de kan komma att ändras när som helst och du bör inte behöva konfigurera dem som tillåtna på din proxyserver.

En proxyserver verifierar den ursprungliga URL:en, som i exemplet ovan är serviceA.office.com och url-adressen inkluderas i Office 365 publicering. Proxyservern begär DNS-upplösningen från URL:en till en IP-adress och tar emot IP_1. Den verifierar inte de mellanliggande CNAME-omdirigeringsposterna.

Hårdkodade konfigurationer eller användning av en lista över tillåtna data som baseras på indirekta Office 365 FQDN rekommenderas inte, stöds inte av Microsoft och det är känt att orsaka anslutningsproblem för kunder. DNS-lösningar som blockerar vid CNAME-omdirigering eller som på annat sätt löser Office 365 DNS-poster kan lösas via DNS-vidarebefordrare med DNS-rekursion aktiverat eller genom att använda DNS-rottips. Många perimeterprodukter från tredje part integrerar rekommenderade inbyggt i Office 365-slutpunkten för att inkludera en lista över tillåtna i konfigurationen med hjälp [av IP-Office 365- och URL-webbtjänsten](microsoft-365-ip-web-service.md)för Office 365.

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Varför visas namn som nsatc.net eller akadns.net i Microsoft-domännamnen?

Office 365 och andra Microsoft-tjänster flera tredjepartstjänster som Akamai och MarkMonitor för att förbättra din Office 365 upplevelsen. För att kunna fortsätta tillhandahålla bästa möjliga upplevelse kan vi komma att ändra dessa tjänster i framtiden. Tredjepartsdomäner kan vara värdar för innehåll, till exempel en CDN, eller så kan de vara värdar för en tjänst, till exempel en geografisk trafikhanteringstjänst. Här är några av de tjänster som vi använder för närvarande:
  
[MarkMonitor](https://www.markmonitor.com/) används när du ser förfrågningar som innehåller *\* .nsatc.net*. Den här tjänsten tillhandahåller skydd av domännamn och övervakning för att skydda mot skadligt beteende.
  
[ExactTarget](https://www.marketingcloud.com/) används när du ser förfrågningar till *\* .exacttarget.com*. Den här tjänsten tillhandahåller hantering av länkar i e-post och övervakning mot skadligt beteende.
  
[Akamai](https://www.akamai.com/) används när du ser förfrågningar som innehåller något av följande FQDN. Den här tjänsten erbjuder tjänster för geo-DNS och innehållsnätverk.
  
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
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Jag måste ha minsta möjliga anslutning för Office 365

Eftersom Office 365 är en uppsättning tjänster som är byggda för att fungera över Internet, utgår vi från att många normala Internettjänster är tillgängliga. Exempelvis måste grundläggande internettjänster som DNS, CRL och CDN kunna nås för att använda Office 365 på samma sätt som de måste kunna nås för att använda de flesta moderna Internettjänster.

Paket Office 365 indets i större tjänsteområden. De kan aktiveras selektivt för anslutning och det finns ett Gemensamt område, som är ett beroende för alla och alltid krävs.

| Serviceområde | Beskrivning |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online och Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online och OneDrive för företag <br/> |
|**Skype för företag Online och Microsoft Teams** <br/> |Skype för företag och Microsoft Teams <br/> |
|**Vanligt** <br/> |Office 365 Pro Plus Office i en webbläsare, Azure AD och andra vanliga nätverksslutpunkter <br/> |

Förutom grundläggande internettjänster finns det tredjepartstjänster som bara används för att integrera funktioner. Även om dessa krävs för integration är de markerade som valfria i artikeln om Office 365-slutpunkter, vilket innebär att tjänstens huvudfunktionalitet kommer att fortsätta att fungera om slutpunkten inte är tillgänglig. Alla nätverksslutpunkter som krävs har attributet obligatoriskt inställt på sant. Alla nätverksslutpunkter som är valfria kommer att ha attributet obligatoriskt inställt på falskt och anteckningsattributet innehåller information om de funktioner som saknas om anslutningen blockeras.
  
Om du försöker använda Office 365 och hittar tjänster från tredje part inte är tillgängliga bör du se till att alla [FQDN](urls-and-ip-address-ranges.md)som är markerade som obligatoriska eller valfria i den här artikeln går igenom proxyn och brandväggen.
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Hur blockerar jag åtkomsten till Microsofts konsumenttjänster?

Du begränsar åtkomsten till våra konsumenttjänster på egen risk. Det enda tillförlitliga sättet att blockera konsumenttjänster är att begränsa åtkomsten till  *det login.live.com*  FQDN. Det här FQDN används av en omfattande uppsättning tjänster, bland annat icke-konsumenttjänster som MSDN, TechNet med flera. Det här FQDN används också av Microsoft Support Secure File Exchange-programmet och är nödvändigt för att överföra filer för att underlätta felsökning för Microsoft-produkter.  Om du begränsar åtkomsten till det här FQDN:t kan det resultera i att du måste inkludera undantag från regeln för nätverksbegäranden som är kopplad till de här tjänsterna.
  
Kom ihåg att blockering av Microsofts konsumenttjänster i sig inte räcker för att förhindra att någon på ditt nätverk för ut information med en Office 365 klientorganisation eller annan tjänst.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Min brandvägg kräver IP-adresser och kan inte bearbeta URL:er. Hur konfigurerar jag den för Office 365?

Office 365 några IP-adresser för alla obligatoriska nätverksslutpunkter. Vissa tillhandahålls endast som URL:er och kategoriseras som standard. URL-adresser i standardkategorin som krävs ska tillåtas via en proxyserver. Om du inte har en proxyserver kan du titta på hur du har konfigurerat webbförfrågningar för URL:er som användare skriver i adressfältet i en webbläsare. användaren inte anger någon IP-adress heller. På Office 365 standardkategori-URL:er som inte tillhandahåller IP-adresser ska konfigureras på samma sätt.

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Microsoft Azure Datacenter IP-intervall](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Krav på nätverksinfrastruktur för Microsoft Intune](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute och Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[Office 365-webbadresser och IP-adressintervall.](urls-and-ip-address-ranges.md)
  
[Hantera ExpressRoute för Office 365 anslutning](managing-expressroute-for-connectivity.md)
  
[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)