---
title: Steg 2. Optimalt nätverk för Microsoft 365 för företags klienter
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
ms.custom:
- Ent_Solutions
description: Optimera nätverks åtkomst till Microsoft 365-klient organisationer.
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908777"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 2. Optimalt nätverk för Microsoft 365 för företags klienter

Microsoft 365 för Enterprise inkluderar moln produktivitets program som team och Exchange Online och Microsoft Intune tillsammans med många identitets-och säkerhets tjänster i Microsoft Azure. Alla de här molnbaserade tjänsterna är beroende av säkerheten, prestandan och tillförlitligheten hos anslutningar från klient enheter i det lokala nätverket eller någon annan plats på Internet. 

För att optimera nätverks åtkomst för din klient organisation måste du:

- Optimera vägen mellan lokala användare och den närmaste platsen till Microsofts globala nätverk.
- Optimera åtkomst till det globala Microsoft-nätverket för fjärran vändare som använder en VPN-lösning för fjärråtkomst.
- Använd Nätverks insikter för att utforma nätverks omkretsen för dina Office-platser.
- Optimera åtkomsten till vissa till gångar som hanteras på SharePoint-webbplatser med Office 365 CDN.
- Konfigurera enheter för proxy och nätverks Edge för att förbigå behandling för betrodd trafik med Microsoft 365 med slut punkter och automatisk uppdatering av listan.

## <a name="enterprise-on-premises-workers"></a>Företags lokala arbetare

För företags nätverk bör du optimera slutanvändarens upplevelse genom att aktivera nätverks åtkomst med högsta prestanda mellan klienter och de närmaste Microsoft 365-slutpunkterna. Slutanvändarens kvalitet är direkt relaterad till prestanda och svars tid för det program som användaren använder. Till exempel är Microsoft Teams beroende av liten latens för att användarna ska kunna ringa samtal, konferenser och samarbeten med samarbete.

Det primära målet i nätverks utformningen bör vara att minimera fördröjningen genom att minska tiden för cirkulering från klient enheter till Microsoft globalt nätverk, Microsofts offentliga nätverks stamnät som sammankopplar alla Microsofts Data Center med låga svars tider, till exempel start punkter för högtillgänglig moln program, som kallas front dörrar, över hela världen.

Här är ett exempel på ett traditionellt företags nätverk.

![Ett traditionellt företags nätverk med central åtkomst till Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

I den här bilden ansluter filial kontor till ett centralt kontor via WAN-enheter och ett WAN-stamnät. Internet åtkomst är via en säkerhets-eller proxyserver på nätverks kontoret och en Internet leverantör. På Internet har Microsofts globala nätverk en serie front dörrar i regioner runt om i världen. Organisationer kan även använda mellanliggande platser för ytterligare paket bearbetning och säkerhet för trafik. En organisations Microsoft 365-innehavare finns i Microsofts globala nätverk.

Problem med den här konfigurationen för Microsoft 365-moln tjänster är:

- För användare i filial kontor skickas trafiken till icke-lokala front dörrar, ökande svars tid.
- Att skicka trafik till mellanliggande platser skapar nätverks-hairpins som utför dubbel paket bearbetning på betrodd trafik, ökande svars tid.
- Nätverks kant enheter utför onödiga och dubbla paket bearbetningar på betrodd trafik, ökande svars tid.

Optimering av nätverks prestanda för Microsoft 365 behöver inte vara komplicerad. Du får bästa möjliga prestanda genom att följa några viktiga principer:

- Identifiera Microsoft 365 nätverks trafik, som är betrodd trafik till Microsofts moln tjänster.
- Tillåt lokal branchning från Microsoft 365-nätverks trafik till Internet från varje plats där användarna ansluter till Microsoft 365.
- Undvik nätverks hairpins.
- Tillåt att Microsoft 365-trafik kringgår enheter för att kontrol lera proxyservrar och paket.

Om du verkställer dessa principer får du ett företags nätverk optimerat för Microsoft 365.

![Ett företags nätverk optimerat för Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

I den här bilden har avdelnings kontor sin egen Internet anslutning via en programdefinierad WAN-enhet (SDWAN) som skickar betrodd Microsoft 365-trafik till den regionala närmaste främre dörren. På Central kontoret gäller inte tillförlitlig Microsoft 365-trafik säkerhets-eller proxyservern och mellanliggande enheter används inte längre.

Så här löses en optimerad konfiguration för ett traditionellt företags nätverk:

- Den betrodda Microsoft 365-trafiken hoppar över WAN-stamnätet och skickas till lokala front dörrar för alla kontor, under tiden för minskad svars tid.
- Nätverks hairpins som utför dubbel paket bearbetning hoppas över för betrodd trafik i Microsoft 365, och minskar svars tiden.
- Nätverks kant enheter som kräver onödiga och dubbel paket bearbetning hoppas över för Microsoft 365-betrodd trafik, vilket minskar svars tiden.

Mer information finns i [Översikt över Microsoft 365-nätverk](../enterprise/microsoft-365-networking-overview.md).

## <a name="remote-workers"></a>Distansarbetare

Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel. Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet. Här är ett exempel.

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

I den här bilden måste Microsoft 365-trafik ta en indirekt väg genom organisationen, som kan vidarekopplas till en Microsoft Global Network-frontend-enhet långt bort från VPN-klientens fysiska plats. Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan. 

Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.

Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen. Mer information finns i avsnitten [Office 365-slutpunkter](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) och [listorna](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) över optimering av kategori slut punkter för delad tunnel.

Här är det resulterande trafikflödet för delade tunnlar, i vilka de flesta trafik till Microsoft 365-molnappar kringgår VPN-anslutningen.

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

I den här bilden skickar VPN-klienten och får viktig tjänst trafik för Microsoft 365-molnet direkt över Internet och till närmaste främre dörr i Microsofts globala nätverk.

Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Använda nätverks insikter (för hands version)

Nätverks insikter är prestanda värden som samlas från din Microsoft 365-klient organisation som hjälper dig att utforma nätverks gränser för dina Office-platser. Varje Insight innehåller information om prestanda i ett angivet problem för varje geografisk plats där lokala användare kommer åt din klient organisation.

Det finns två nätverks insikter för klient organisations nivå som kan visas för klient organisationen:

- [Exchange-sampel som påverkas av anslutnings problem](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint-sampel som påverkas av anslutnings problem](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Det här är särskilda nätverks insikter för varje Office-plats:

- [Utgående nätverks utgångar](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Bättre prestanda upptäckt för kunder nära dig](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Användning av en icke optimal Exchange Online-onlinetjänst](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint Online-onlinetjänst](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Liten nedladdnings hastighet från SharePoint-startdörren](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Kina-användarens optimala nätverks utgång](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 visas för närvarande. Det är endast tillgängligt för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.

Mer information finns i [Microsoft 365 nätverks insikter](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint-prestanda med Office 365 CDN

Med ett molnbaserade innehålls leverans nätverk (CDN) kan du minska inläsnings tid, spara bandbredd och snabba svar. En CDN förbättrar prestandan genom att cachelagra statiska till gångar, till exempel grafik-eller videofiler, i webbläsare som begär dem, vilket gör det enklare att ladda ner nedladdningar och minska svars tiden. Du kan använda det inbyggda Office 365 Content Delivery Network (CDN), som ingår i SharePoint i Microsoft 365 E3 och E5, för att hantera statiska till gångar för bättre prestanda för SharePoint-sidorna.

Office 365 CDN består av flera CDN som låter dig hantera fasta till gångar på flera platser, eller _ursprung_, och betjäna dem från globala nätverk med snabb hastighet. Beroende på vilken typ av innehåll du vill ha i Office 365 CDN kan du lägga till **offentliga** ursprung, **privata** ursprung eller både och.

När du distribuerat och konfigurerat laddar Office 365 CDN upp till gångar från offentliga och privata ursprung och gör dem tillgängliga för snabb åtkomst till användare som finns på Internet.

![Office 365 CDN distribuerat för användare](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN distribuerat för användare")

Mer information finns i [använda Office 365 CDN med SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).

## <a name="automated-endpoint-listing"></a>Automatisk slut punkts listning

Om du vill att dina lokala klienter, kant enheter och molnbaserade paket analys tjänster ska hoppa över bearbetning av betrodd Microsoft 365-trafik måste du konfigurera dem med slut punkter (IP-adressintervall och DNS-namn) som motsvarar Microsoft 365-tjänsterna. Dessa slut punkter kan konfigureras manuellt i brand väggar och andra Edge-säkerhetsenheter, PAC-filer för klient datorer för att kringgå proxyservrar eller SD-WAN-enheter hos filialer. Slut punkterna ändras emellertid med tiden och kräver kontinuerligt manuellt underhåll av slut punkts listorna på dessa platser.

Om du vill automatisera visningen av list-och ändrings hantering för Microsoft 365-slutpunkter i klientens PAC-filer och nätverks enheter kan du använda [Office 365 IP-adress och övrig URL-baserad webb tjänst](../enterprise/microsoft-365-ip-web-service.md). Denna tjänst hjälper dig att bättre identifiera och skilja på Microsoft 365-nätverks trafik, vilket gör det lättare för dig att utvärdera, konfigurera och hålla sig uppdaterad med de senaste ändringarna.

Du kan använda PowerShell, python eller andra språk för att ta reda på ändringar av slut punkter över tiden och konfigurera dina PAC-filer och nätverks enheter för Edge.

Den grundläggande processen är:

1. Använd Office 365 IP Address and URL web service och konfigurations mekanismen för att konfigurera dina PAC-filer och nätverks enheter med den aktuella uppsättningen av Microsoft 365-slutpunkter.
2. Kör en daglig återkommande för att kontrol lera ändringar av slut punkterna eller Använd en meddelande metod.
3. När ändringar identifieras kan du återskapa och distribuera PAC-filen för klient datorer och göra ändringarna på dina nätverks enheter.

Mer information finns i [Office 365 IP Address and URL Web Service](../enterprise/microsoft-365-ip-web-service.md).

## <a name="results-of-step-2"></a>Resultat av steg 2

För din Microsoft 365-klient med optimalt nätverk har du bestämt:

- Hur du optimerar nätverks prestanda för lokala användare genom att lägga till Internet anslutningar till alla filial kontor och eliminera nätverks hairpins.
- Implementera automatisk lista över betrodda slut punkter för klientbaserade PAC-filer och nätverks enheter och-tjänster, inklusive pågående uppdateringar (mest passande för företags nätverk).
- Så här kan du få åtkomst till fjärranslutna kollegor till lokala resurser.
- Använda nätverks insikter
- Så här distribuerar du Office 365 CDN.

Här är ett exempel på en företags organisation och dess innehavare med optimala nätverksfunktioner.

![Exempel på en klient organisation med optimalt nätverk](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

I den här bilden har innehavaren för företags organisationen:

- Lokal Internet åtkomst för varje filial kontor med en SDWAN-enhet som vidarebefordrar betrodd Microsoft 365-trafik till en lokal front dörr.
- Inga nätverks hairpins.
- Centrala Office-säkerhetsfunktioner och-nätenheter som vidarebefordrar Microsoft 365-tillförlitliga trafik till en lokal front dörr.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Kontinuerligt underhåll för optimala nätverk

Kontinuerligt måste du kanske:

- Uppdatera dina gräns enheter och distribuerade PAC-filer för ändringar i slut punkter eller kontrol lera att din automatiserade process fungerar korrekt.
- Hantera dina till gångar i Office 365 CDN.
- Uppdatera delnings konfigurationen för delade tunnlar på dina VPN-klienter för ändringar i slut punkter.

## <a name="next-step"></a>Nästa steg

[![Steg 3. Synkronisera dina identiteter och påtvinga säkra inloggningar](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Fortsätt med [identiteten](tenant-management-identity.md) för att synkronisera dina lokala konton och grupper och påtvinga säkra användar inloggningar.
