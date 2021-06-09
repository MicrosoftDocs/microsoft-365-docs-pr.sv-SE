---
title: Steg 2. Optimala nätverk för din Microsoft 365 för företagsklienter
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Optimera nätverksåtkomsten till dina Microsoft 365 klienter.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407198"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 2. Optimala nätverk för din Microsoft 365 för företagsklienter

Microsoft 365 för företag inkluderar molnproduktivitetsprogram som Teams och Exchange Online, Microsoft Intune, tillsammans med många identitets- och säkerhetstjänster för Microsoft Azure. Alla dessa molnbaserade tjänster förlitar sig på säkerhet, prestanda och tillförlitlighet i anslutningar från klientenheter i det lokala nätverket eller på valfri plats på Internet. 

Om du vill optimera nätverksåtkomsten för din klientorganisation måste du:

- Optimera sökvägen mellan dina lokala användare och den närmaste platsen för Microsofts globala nätverk.
- Optimera åtkomsten till Microsofts globala nätverk för dina fjärranvändare som använder en VPN-lösning för fjärråtkomst.
- Använd Nätverksinsikter för att utforma nätverks perimeter för dina kontorsplatser.
- Optimera åtkomsten till specifika tillgångar på SharePoint webbplatser med Office 365 CDN.
- Konfigurera proxy- och nätverkets edge-enheter för att kringgå Microsoft 365 betrodd trafik med listan med slutpunkter och automatisera uppdateringen av listan när ändringar görs.

## <a name="enterprise-on-premises-workers"></a>Lokalt anställda i företag

För företagsnätverk bör du optimera slutanvändarupplevelsen genom att ge bästa möjliga nätverksåtkomst mellan klienter och närmaste Microsoft 365 slutpunkter. Slutanvändarupplevelsens kvalitet är direkt relaterad till prestanda och svarstiden för programmet som användaren använder. Till exempel Microsoft Teams lite fördröjning så att användarnas telefonsamtal, konferenser och samarbete på delad skärm blir problemfria.

Det primära målet i nätverksdesignen bör vara att minimera svarstiden genom att minska tidsfördröjning för returer (ROUND-trip time, RTT) från klientenheter till Microsoft Global Network, Microsofts offentliga stamnät som sammanbinder alla Microsofts datacenter med låg latens, inmatningspunkter i molnprogrammet med hög tillgänglighet, så kallade front dörrar, utspridda över hela världen.

Här är ett exempel på ett traditionellt företagsnätverk.

![Ett traditionellt företagsnätverk med central åtkomst till Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

I den här illustrationen ansluter filialer till ett centralt kontor via WAN-enheter (Wide Area Network) och ett WAN-stamnät. Internetanslutningen är via en säkerhets- eller proxyenhet vid nätverkskanten på det centrala kontoret och en Internetleverantör (ISP). På Internet har Microsoft Global Network en serie dörrar fram i områden runt om i världen. Organisationer kan också använda mellanliggande platser för ytterligare paketbearbetning och säkerhet för trafik. En organisations klientorganisation Microsoft 365 i Microsofts globala nätverk.

Problemen med den här konfigurationen för Microsoft 365 molntjänster är:

- För användare på filialkontor skickas trafiken till icke-lokala dörrar, vilket ökar svarstiden.
- Om du skickar trafik till mellanliggande platser skapas nätverk hårnålsfiler som utför duplicerad paketbearbetning på betrodd trafik, vilket ökar svarstiden.
- Nätverk edge-enheter utför obevakad och duplicerad paketbearbetning på betrodd trafik, öka svarstiden.

Det behöver Microsoft 365 att optimera nätverksprestandan. Du får bästa möjliga prestanda genom att följa några viktiga principer:

- Identifiera Microsoft 365, som är betrodd trafik med Microsofts molntjänster som destination.
- Tillåt lokal grenens utgående trafik Microsoft 365 nätverkstrafik till Internet från varje plats där användarna ansluter till Microsoft 365.
- Undvik hårnålsnätverk.
- Tillåt Microsoft 365 att förbikoppla proxy proxy och paketinspektionsenheter.

Om du implementerar de här principerna får du ett företagsnätverk optimerat för Microsoft 365.

![Ett företagsnätverk som är optimerat för Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

I den här illustrationen har filialer sin egen Internetanslutning genom en programvarudefinierad WAN-enhet (SDWAN), som skickar tillförlitlig Microsoft 365-trafik till den regionala närmaste fronten. På det centrala kontoret kringgår betrodda Microsoft 365 säkerhets- eller proxyenheter och mellanliggande enheter används inte längre.

Så här löser den optimerade konfigurationen problem med svarstiden för ett traditionellt företagsnätverk:

- Betrodd Microsoft 365 trafik hoppar över WAN-stamnätet och skickas till lokala dörrar fram för alla kontor, vilket minskar svarstiden.
- Nätverk hårnålsfiler som utför duplicerad paketbearbetning hoppas Microsoft 365 för betrodd trafik, vilket minskar svarstiden.
- Nätverk edge-enheter som utför obevakad och duplicerad paketbearbetning hoppas över för Microsoft 365 betrodd trafik, minskande svarstid.

Mer information finns i Microsoft 365 [översikt över nätverksanslutningen.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Distansarbetare

Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel. Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet. Här är ett exempel.

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

I den här illustrationen måste Microsoft 365-trafiken ta en indirekt väg genom organisationen, som kan vidarebefordras till en Microsoft Global Network-klient så långt borta från VPN-klientens fysiska plats. Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan. 

Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.

Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen. Mer information finns i Office 365 [för slutpunktskategorier](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) [och listorna](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) med optimera kategorislutpunkter för delade tunnlar.

Här är det resulterande trafikflödet för delade tunnlar, där den största delen av trafiken till Microsoft 365-molnappar kringgår VPN-anslutningen.

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

I den här illustrationen skickar VPN-klienten och tar emot viktig Microsoft 365-molntjänsttrafik direkt via Internet och till närmaste klient till Microsofts globala nätverk.

Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Använda Nätverksinsikter (förhandsversion)

Nätverksinsikter är prestandamätvärden som samlas Microsoft 365 klientorganisation som hjälper dig att utforma nätverks perimeter för kontorsplatserna. Varje insikt ger detaljerad information om prestandaegenskaperna för ett visst problem för varje geografisk plats där lokala användare har åtkomst till din klientorganisation.

Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för klientorganisationen:

- [Exchange exempel på anslutningar som påverkas av anslutningsproblem](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint exempel på anslutningar som påverkas av anslutningsproblem](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Det här är specifika nätverksinsikter för varje kontorsplats:

- [Backhauled network egress](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Bättre prestanda som upptäckts för kunder nära dig](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Användning av en icke-optimal Exchange Online tjänst framifrån](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint för onlinetjänster](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Låg nedladdningshastighet SharePoint fronten](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Optimal utgående nätverkstrafik för användare i Kina](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i administrationscentret Microsoft 365 finns för närvarande i förhandsgranskningsstatus. Det är bara tillgängligt för Microsoft 365 som har registrerats i programmet för funktionsförhandsgranskning.

Mer information finns i [Microsoft 365 Network Insights.](../enterprise/office-365-network-mac-perf-insights.md)

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint med Office 365 CDN

En molnbaserad Content Delivery Network (CDN) gör att du kan minska belastningstiden, spara bandbredd och snabba svarstider. En CDN förbättrar prestanda genom att cachelagra statiska tillgångar, till exempel grafik- eller videofiler, närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningarna och minska svarstiden. Du kan använda den inbyggda Office 365 Content Delivery Network (CDN), som ingår i SharePoint i Microsoft 365 E3 och E5, för att lagra statiska tillgångar för att få bättre prestanda för dina SharePoint-sidor.

The Office 365 CDN består av flera CDN som gör att du kan ha statiska tillgångar på flera platser, eller _ursprung,_ och hantera dem från globala nätverk med hög hastighet. Beroende på vilken typ av innehåll som du vill lagra  i Office 365 CDN kan du lägga till offentliga **ursprung,** privata ursprung eller båda.

När de distribueras och konfigureras laddar Office 365 CDN tillgångar upp från offentliga och privata ursprung och gör dem tillgängliga för snabb åtkomst till användare på internet.

![Office 365 CDN distribuerats för användare](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN distribuerats för användare")

Mer information finns i [Använda Office 365 CDN med SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Automatiserad slutpunktslistning

Om du vill att dina lokala klienter, edge-enheter och molnbaserade paketanalystjänster ska hoppa över bearbetningen av betrodd Microsoft 365-trafik måste du konfigurera dem med de slutpunkter (IP-adressintervall och DNS-namn) som motsvarar Microsoft 365-tjänsterna. Dessa slutpunkter kan konfigureras manuellt i brandväggar och andra gränssäkerhetsenheter, PAC-filer för klientdatorer för att kringgå proxyenheter eller SD-WAN-enheter på filialer. Slutpunkterna ändras emellertid med tiden, vilket kräver löpande manuellt underhåll av slutpunktslistorna på dessa platser.

Använd IP-adress- och URL-Microsoft 365-baserade webbtjänsten för att automatisera list- och ändringshantering för Office 365 Microsoft 365-slutpunkter i dina klient-PAC-filer och [nätverksenheter.](../enterprise/microsoft-365-ip-web-service.md) Den här tjänsten hjälper dig att bättre identifiera och skilja Microsoft 365 nätverkstrafik, vilket gör det enklare för dig att utvärdera, konfigurera och hålla dig aktuell med de senaste ändringarna.

Du kan använda PowerShell, Python eller andra språk för att avgöra ändringar av slutpunkter över tid och konfigurera PAC-filer och edge-nätverksenheter.

Så här gör du:

1. Använd Office 365 IP-adress och URL-webbtjänst och den konfigurationsmekanism du väljer för att konfigurera PAC-filer och nätverksenheter med den aktuella uppsättningen Microsoft 365 slutpunkter.
2. Kör ett dagligt återkommande för att söka efter ändringar i slutpunkterna eller använda en aviseringsmetod.
3. När ändringar upptäcks återskapar och distribuerar du PAC-filen till klientdatorerna och gör ändringarna på dina nätverksenheter.

Mer information finns i Office 365 [ip-adress och URL-webbtjänst.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Resultat av steg 2

För din Microsoft 365 med optimala nätverk har du fastställt:

- Optimera nätverksprestandan för lokala användare genom att lägga till Internetanslutningar till alla filialkontor och ta bort hårnålsanslutning i nätverket.
- Så här implementerar du automatiska betrodda slutpunktslistor för dina klientbaserade PAC-filer och dina nätverksenheter och -tjänster, inklusive pågående uppdateringar (mest lämpliga för företagsnätverk).
- Hur du kan ge distansarbetare tillgång till lokala resurser.
- Använda Nätverksinsikter
- Hur du distribuerar Office 365 CDN.

Här är ett exempel på en företagsorganisation och dess klientorganisation med optimala nätverksfunktioner.

![Exempel på en klientorganisation med optimala nätverk](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

I den här illustrationen har klientorganisationen för den här företagsorganisationen:

- Lokal internetanslutning för varje filialkontor med en SDWAN-enhet som vidarebefordrar betrodda Microsoft 365 trafik till en lokal front dörr.
- Inga hårnålsnätverk.
- Centrala enheter för kontorssäkerhet och proxy-edge som vidarebefordrar Microsoft 365 betrodd trafik till en lokal ytterkant.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Löpande underhåll för optimala nätverk

Du kan behöva:

- Uppdatera dina edge-enheter och distribuerade PAC-filer för ändringar i slutpunkter eller kontrollera att din automatiserade process fungerar som den ska.
- Hantera dina tillgångar i Office 365 CDN.
- Uppdatera konfigurationen för delade tunnlar i dina VPN-klienter för ändringar i slutpunkter.

## <a name="next-step"></a>Nästa steg

[![Steg 3. Synkronisera dina identiteter och tillämpa säkra inloggningar](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Fortsätt med [identitet](tenant-management-identity.md) för att synkronisera dina lokala konton och grupper och tillämpa säkra användar inloggningar.
