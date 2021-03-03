---
title: Steg 2. Optimala nätverk för dina klientorganisationar i Microsoft 365 för företag
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
description: Optimera nätverksåtkomsten till dina Microsoft 365-innehavare.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407198"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 2. Optimala nätverk för dina klientorganisationar i Microsoft 365 för företag

Microsoft 365 för företag innehåller produktivitetsprogram för molnet, till exempel Teams och Exchange Online och Microsoft Intune, samt många identitets- och säkerhetstjänster för Microsoft Azure. Alla dessa molnbaserade tjänster förlitar sig på säkerhet, prestanda och tillförlitlighet i anslutningar från klientenheter i ditt lokala nätverk eller valfri plats på Internet. 

Om du vill optimera nätverksåtkomst för klientorganisationen måste du:

- Optimera sökvägen mellan dina lokala användare och den närmaste platsen för Microsofts globala nätverk.
- Optimera åtkomsten till Microsofts globala nätverk för dina fjärranvändare som använder en VPN-lösning för fjärråtkomst.
- Använd Nätverksinsikter för att utforma nätverks perimeter för dina kontorsplatser.
- Optimera åtkomsten till specifika tillgångar på SharePoint-webbplatser med Office 365 CDN.
- Konfigurera proxy- och nätverks-edge-enheter för att kringgå bearbetning för Microsoft 365-betrodd trafik med listan med slutpunkter och automatisera uppdateringen av listan när ändringar görs.

## <a name="enterprise-on-premises-workers"></a>Företagsanställda lokalt

För företagsnätverk bör du optimera slutanvändarupplevelsen genom att aktivera nätverksåtkomst med högsta möjliga prestanda mellan klienter och de närmaste Microsoft 365-slutpunkterna. Kvaliteten på slutanvändarupplevelsen är direkt relaterad till prestanda och svarstiden för programmet som användaren använder. Microsoft Teams förlitar sig till exempel på låg fördröjning så att användarnas telefonsamtal, konferenser och samarbete på delad skärm blir felfria.

Det primära målet i nätverksdesignen bör vara att minimera svarstiden genom att minska tidsfördröjningstid (ROUND-trip time, RTT) från klientenheter till Microsoft Global Network, Microsofts offentliga stamnät som sammanbinder alla Microsofts datacenter med låg latens, startpunkter för molnprogram med hög tillgänglighet, så kallade fram dörrar, utspridda över hela världen.

Här är ett exempel på ett traditionellt företagsnätverk.

![Ett traditionellt företagsnätverk med central tillgång till Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

I den här illustrationen ansluter filialer till ett centralt kontor via WAN-enheter (Wide Area Network) och ett WAN-stamnät. Internetanslutningen är via en säkerhets- eller proxyenhet vid nätverkskanten på det centrala kontoret och en Internet-tjänstprovider (ISP). På Internet har Microsoft Global Network en serie dörrar fram i områden runt om i världen. Organisationer kan också använda mellanliggande platser för ytterligare paketbearbetning och säkerhet för trafik. En organisations Microsoft 365-innehavare finns i Microsofts globala nätverk.

Problemen med den här konfigurationen för Microsoft 365-molntjänsterna är:

- För användare på filialkontor skickas trafiken till icke-lokala dörrar, och ökar svarstiden.
- Om du skickar trafik till mellanliggande platser skapas nätverksnålsnålar som utför duplicerad paketbearbetning på betrodd trafik och ökar svarstiden.
- Nätverk edge-enheter utför oläst och duplicerad paketbearbetning på betrodd trafik, ökande svarstid.

Det behöver inte vara svårt att optimera Microsoft 365-nätverksprestandan. Du får bästa möjliga prestanda genom att följa några viktiga principer:

- Identifiera Microsoft 365-nätverkstrafik som är betrodd trafik till Microsofts molntjänster.
- Tillåt lokal branchning av Microsoft 365-nätverkstrafik till Internet från varje plats där användarna ansluter till Microsoft 365.
- Undvik hårnålsklipp i nätverket.
- Tillåt Att Microsoft 365-trafik kringgå proxy proxy- och paketinspektionsenheter.

Om du implementerar de här principerna får du ett företagsnätverk optimerat för Microsoft 365.

![Ett företagsnätverk optimerat för Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

I den här illustrationen har filialkontor sin egen Internetanslutning via en programvarudefinierad WAN-enhet (SDWAN), som skickar betrodd Microsoft 365-trafik till den regionala närmaste ytterporten. På det centrala kontoret går betrodd Microsoft 365-trafik förbi säkerheten eller proxyenheten och mellanliggande enheter används inte längre.

Så här löser den optimerade konfigurationen problem med fördröjning i ett traditionellt företagsnätverk:

- Betrodd Microsoft 365-trafik hoppar över WAN-stamnätet och skickas till lokal dörrar för alla kontor, vilket minskar svarstiden.
- Nätverkshårsnålar som utför duplicerad paketbearbetning hoppas över för Microsoft 365-betrodd trafik och minskar svarstiden.
- Nätverk edge-enheter som utför obevakad och duplicerad paketbearbetning hoppas över för Microsoft 365-betrodd trafik, vilket minskar svarstiden.

Mer information finns i [översikten över Microsoft 365-nätverksanslutning.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Distansarbetare

Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel. Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet. Här är ett exempel.

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

I den här illustrationen måste Microsoft 365-trafiken ta en indirekt väg genom din organisation som kan vidarebefordras till en av Microsoft Global Networks frontporter långt ifrån VPN-klientens fysiska plats. Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan. 

Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.

Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen. Mer information finns i Office [365-slutpunktskategorier](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) och [listorna för](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) optimera kategorislutpunkter för delade tunnlar.

Här är det resulterande trafikflödet för delade tunnlar, där större delen av trafiken till Microsoft 365-molnappar kringgår VPN-anslutningen.

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

I den här illustrationen skickar VPN-klienten och får viktig Microsoft 365-molntjänsttrafik direkt via Internet och till närmaste klient så att det går in i Microsoft Global Network.

Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Använda Nätverksinsikter (förhandsversion)

Nätverksinsikter är prestandamått som samlas in från din Microsoft 365-klientorganisation som hjälper dig att utforma nätverks perimeter för dina kontor. Varje insikt ger direktinformation om prestandaegenskaperna för ett visst problem för varje geografisk plats där lokala användare har åtkomst till din klientorganisation.

Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för innehavaren:

- [Exempel på Exchange-anslutningar som påverkas av anslutningsproblem](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint-exempelanslutningar som påverkas av anslutningsproblem](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Det här är de specifika nätverksinsikterna för varje kontor:

- [Utgående nätverksback](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Bättre prestanda upptäckt för kunder nära dig](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Användning av en icke-optimal Exchange Online-tjänsts framsida](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint Online-tjänsts framsida](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Låg nedladdningshastighet från SharePoints dörr](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Optimal utgående nätverkstrafik för användare i Kina](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i Administrationscenter för Microsoft 365 finns för närvarande i förhandsgranskningsstatus. Den är bara tillgänglig för Microsoft 365-innehavare som har registrerats i förhandsgranskningsprogrammet för funktioner.

Mer information finns i [Microsoft 365 Network Insights.](../enterprise/office-365-network-mac-perf-insights.md)

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint-prestanda med Office 365 CDN

Ett molnbaserat nätverk för innehållsleverans (CDN) gör att du kan minska inläsningstiden, spara bandbredd och snabba svarstider. Ett CDN förbättrar prestanda genom cachelagring av statiska tillgångar, till exempel grafik- eller videofiler närmare de webbläsare som begär dem, vilket hjälper till att snabba på hämtningar och minska svarstiden. Du kan använda det inbyggda nätverket för innehållsleverans i Office 365 (CDN), som ingår i SharePoint i Microsoft 365 E3 och E5, för att lagra statiska tillgångar för att ge bättre prestanda för dina SharePoint-sidor.

Office 365 CDN består av flera CDN:er som gör att du kan lagra statiska tillgångar på flera platser, eller ursprung, och tjäna dem från globala _höghastighetsnätverk._ Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till offentliga **ursprung,** privata ursprung eller båda. 

När Office 365 CDN distribueras och konfigureras laddar det upp tillgångar från offentliga och privata ursprung och gör dem tillgängliga för snabb åtkomst till användare på Internet.

![Office 365 CDN distribuerat för användare](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN distribuerat för användare")

Mer information finns i Använda [Office 365 CDN med SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Automatiserad slutpunktslista

Om du vill att dina lokala klienter, edge-enheter och molnbaserade paketanalystjänster ska hoppa över bearbetningen av betrodd Microsoft 365-trafik måste du konfigurera dem med den uppsättning slutpunkter (IP-adressintervall och DNS-namn) som motsvarar Microsoft 365-tjänster. Dessa slutpunkter kan konfigureras manuellt i brandväggar och andra edge-säkerhetsenheter, PAC-filer för klientdatorer för att kringgå proxyenheter eller SD-WAN-enheter på filialkontor. Slutpunkterna ändras dock över tid, vilket kräver löpande manuellt underhåll av slutpunktslistorna på dessa platser.

För att automatisera list- och ändringshanteringen för Microsoft 365-slutpunkter i klientens PAC-filer och nätverksenheter använder du [IP-adressen och URL REST-baserade webbtjänsten för Office 365.](../enterprise/microsoft-365-ip-web-service.md) Den här tjänsten hjälper dig att bättre identifiera och särskilja Microsoft 365-nätverkstrafik, vilket gör det enklare för dig att utvärdera, konfigurera och hålla dig aktuell med de senaste ändringarna.

Du kan använda PowerShell, Python eller andra språk för att fastställa ändringar av slutpunkter över tid och konfigurera PAC-filer och edge-nätverksenheter.

Så här gör du:

1. Använd IP-adress- och URL-webbtjänsten för Office 365 och valfri konfigurationsmekanism för att konfigurera PAC-filer och nätverksenheter med den aktuella uppsättningen Microsoft 365-slutpunkter.
2. Kör ett dagligt återkommande för att söka efter ändringar i slutpunkterna eller använda en aviseringsmetod.
3. När ändringar upptäcks, återskapas och distribueras PAC-filen på nytt för klientdatorer och gör ändringarna på dina nätverksenheter.

Mer information finns i [Office 365 IP-adress och URL-webbtjänst.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Resultat av steg 2

För din Microsoft 365-klientorganisation med optimala nätverk har du fastställt:

- Optimera nätverksprestanda för lokala användare genom att lägga till Internetanslutningar till alla filialkontor och ta bort nätverkshårsnålar.
- Så här implementerar du automatiska betrodda slutpunktslistor för dina klientbaserade PAC-filer och dina nätverksenheter och -tjänster, inklusive pågående uppdateringar (passar bäst för företagsnätverk).
- Hur du ger distansarbetare tillgång till lokala resurser.
- Så här använder du Nätverksinsikter
- Distribuera Office 365 CDN.

Här är ett exempel på en stor verksamhet och dess klientorganisation med optimala nätverksfunktioner.

![Exempel på en klientorganisation med optimala nätverk](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

I den här illustrationen har klientorganisationen för den här företagsorganisationen:

- Lokal internetåtkomst för varje filial med en SDWAN-enhet som vidarebefordrar betrodd Microsoft 365-trafik till en lokal dörr.
- Inga hårnålsnätverk.
- Centrala office-säkerhet och proxy-edge-enheter som vidarebefordrar Microsoft 365-betrodd trafik till en lokal dörr.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Löpande underhåll för optimala nätverk

Du kan kontinuerligt behöva:

- Uppdatera dina edge-enheter och distribuerade PAC-filer för ändringar i slutpunkter eller kontrollera att din automatiserade process fungerar som den ska.
- Hantera dina tillgångar i Office 365 CDN.
- Uppdatera konfigurationen för delade tunnlar i dina VPN-klienter för ändringar i slutpunkter.

## <a name="next-step"></a>Nästa steg

[![Steg 3. Synkronisera dina identiteter och tillämpa säkra inloggningar](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Fortsätt med [identitet](tenant-management-identity.md) för att synkronisera dina lokala konton och grupper och se till att du använder säkra inloggningar.
