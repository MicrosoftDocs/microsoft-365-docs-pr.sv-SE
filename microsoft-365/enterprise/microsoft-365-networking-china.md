---
title: Prestandaoptimering av globala klientorganisationen för Kina-användare av Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Den här artikeln innehåller vägledning för hur du optimerar nätverksprestanda för Kina-användare av globala Microsoft 365-klientorganisationar.
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615201"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Prestandaoptimering av globala klientorganisationen för Kina-användare av Microsoft 365

>[!IMPORTANT]
>Den här vägledningen är specifik för användningsscenarier där **Microsoft 365-företagsanvändare** i Kina ansluter till en **global Microsoft 365-klientorganisation.** Den här **vägledningen gäller** inte för klientorganisationen i Office 365 som drivs av 21Vianet.

För företag med globala Microsoft 365-klientprogram och företagsnärvaro i Kina kan Microsoft 365-klientprestandan för kinabaserade användare vara komplicerad av faktorer som är unika för China Telcos Internetarkitektur.

Kinas internetleverantörer har reglerat anslutningar till det globala offentliga Internet som går genom perimeterenheter som ofta blir överbelastade i olika gränsnätverk. Den här överbelastningen skapar paketförlust och svarstid för all Internettrafik som går till och från Kina.

![Microsoft 365-trafik – inte optimerad](../media/O365-networking/China-O365-unoptimized.png)

Paketförluster och -svarstider innebär skadliga prestanda för nätverkstjänster, särskilt tjänster som kräver stora datautbyten (t.ex. stora filöverföringar) eller kräver nära realtidsprestanda (ljud- och videoprogram).

Syftet med det här avsnittet är att tillhandahålla metodtips för att minska påverkan på korsnätverksstockningar i Kina på Microsoft 365-tjänster. Det här avsnittet tar inte upp andra vanliga prestandaproblem på sista biten, till exempel problem med hög paketfördröjning på grund av komplex routning inom Kina-operatörer.

## <a name="corporate-network-best-practices"></a>Metodtips för företagsnätverk

Många företag med globala Microsoft 365-klientorganisationar och användare i Kina har implementerat privata nätverk som har företagsnätverkstrafik mellan kontor i Kina och kontorsplatser runt om i världen. Dessa företag kan utnyttja den här nätverksinfrastrukturen för att undvika nätverksstockningar över gränserna och optimera Microsoft 365-tjänstprestandan i Kina.

>[!IMPORTANT]
>Som med alla privata WAN-implementeringar bör du alltid följa kraven i lagstiftningen för ditt land och/eller din region för att säkerställa att nätverkskonfigurationen är i regel.

Som ett första steg är det centralt att du följer våra riktvärdesnätverksvägledning i Nätverksplanering och [prestandajustering för Microsoft 365.](./network-planning-and-performance.md) Det primära målet bör vara att undvika att få tillgång till globala Microsoft 365-tjänster från Internet i Kina, om möjligt.

- Använd ditt befintliga privata nätverk för att överföra Microsoft 365-nätverkstrafik mellan Kinas office-nätverk och platser för trådlös anslutning till det offentliga Internet utanför Kina. Nästan alla platser utanför Kina ger en tydlig fördel. Nätverksadministratörer kan optimera ytterligare genom att gå ut i områden med låg fördröjning som är sammankopplade med [Microsofts globala nätverk.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hongkong, Japan och Sydkorea är exempel.
- Konfigurera användarenheter för åtkomst till företagsnätverket via en VPN-anslutning så att Microsoft 365-trafik kan ta dig via företagsnätverkets privata länk. Se till att VPN-klienter antingen inte är konfigurerade för delade tunnlar eller att användarenheter är konfigurerade för att ignorera delade tunnlar för Microsoft 365-trafik. Mer information om hur du optimerar VPN-anslutning för Teams och realtidsmediatrafik finns i [det här avsnittet.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- Konfigurera nätverket för att dirigera all Microsoft 365-trafik via din privata länk. Om du måste minimera mängden trafik via din privata länk kan du välja att endast  dirigera  slutpunkter i kategorin Optimera och tillåta förfrågningar om att tillåta och standardslutpunkter för att skicka internet.  Det förbättrar prestanda och minimerar bandbreddsanvändningen genom att begränsa optimerad trafik till viktiga tjänster som är mest känsliga för hög fördröjning och paketförlust.
- Om möjligt bör du använda UDP i stället för TCP för direktuppspelad mediatrafik, till exempel för Teams. UDP erbjuder bättre prestanda för direktuppspelning av media än TCP.

Mer information om hur du selektivt dirigerar Microsoft 365-trafik finns i [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md). En lista över alla URL:er och IP-adresser för Office 365 finns i URL-adresser och IP-adressintervall för [Office 365.](urls-and-ip-address-ranges.md)

![Microsoft 365-trafik – optimerad](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Metodtips för användare

Användare i Kina som ansluter till globala Microsoft 365-klientorganisationsplatser från fjärranslutna platser som hem, caféer, hotell och filialkontor utan anslutning till företagsnätverk kan uppleva dålig nätverksprestanda eftersom trafiken mellan deras enheter och Microsoft 365 måste ta fram Kinas överbelastade korsgränsade nätverkskretsar.

Om det inte går att använda privata nätverk över kantlinjer och/eller VPN-åtkomst till företagsnätverket kan prestandaproblem per användare fortfarande minimeras om dina kinabaserade användare utbildas så att de kan följa de här metodtipsen.

- Använd avancerade Office-klienter som har stöd för cachelagring (t.ex. Outlook, Teams, OneDrive osv.) och undvik webbaserade klienter. Cachelagring av Office-klient och offlineåtkomstfunktioner kan avsevärt minska effekterna av nätverksstockningar och svarstider.
- Om Microsoft 365-klientorganisationen har  konfigurerats med ljudkonferensfunktionen kan Teams-användare ansluta till möten via PSTN (public switched telephone network). Mer information finns i [Ljudkonferens i Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Om användare har problem med nätverksprestanda bör de rapportera till IT-avdelningen för felsökning och eskalera till Microsoft-support om problem med Microsoft 365-tjänster är misstänkt. Alla problem orsakas inte av nätverksprestanda över kantlinjer.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Optimera nätverksprestandan för Microsoft Teams-möten för användare i Kina  

För organisationer med globala Microsoft 365-klientorganisationer och närvaro i Kina kan Microsoft 365-klientprestanda för Kina-baserade användare vara komplicerat av faktorer som är unika för Internetarkitekturen i Kina. Många företag och skolor har rapporterat ett bra resultat genom att följa den här vägledningen. Omfattningen är emellertid begränsad till användarnätverksplatser som är under kontroll av IT-nätverkskonfigurationen, till exempel kontorsplatser eller hem-/mobilslutpunkter med VPN-anslutning. Microsoft Teams-samtal och -möten används ofta från externa platser, t.ex. hemkontor, mobila platser, på väg, och caféer. Eftersom samtal och möten förlitar sig på mediatrafik i realtid är de här Teams-upplevelserna särskilt känsliga för nätverksstockningar.

Microsoft samarbetar därför med telekommunikationsleverantörer för att överföra realtidstrafik i Teams och Skype för företag – Online med en mer högkvalitativ nätverkssökväg mellan nationella och offentliga Internetanslutningar i Kina och Teams- och Skype-tjänster i det globala molnet i Microsoft 365. Den här funktionen har lett till en mer än tiod vikning av paketförlusten och andra viktiga värden som påverkar användarens upplevelse.

>[!IMPORTANT]
>För närvarande går inte de här förbättringarna in på Microsoft Live Events-möten, till exempel stora sändningsmöten eller "stadslokalen"-möten i Teams eller Microsoft Stream. Om du vill visa ett Live Events-möte måste användare i Kina använda ett privat nätverk eller SDWAN/VPN-lösning. Men förbättringarna i nätverket kommer att vara till nytta för användare som presenterar eller skapar ett live-evenemangsmöte, eftersom den upplevelsen fungerar som ett vanligt Teams-möte för producent eller presentatör.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Metodtips för organisationsnätverk för Teams-möten

Du måste fundera på hur du ska utnyttja dessa nätverksförbättringar, eftersom den föregående vägledningen bör vara att överväga ett privat nätverkstillägg för att undvika nätverksstockningar över gränserna. Det finns två allmänna alternativ för organisation av Office-nätverk:

1.  Gör ingenting nytt. Fortsätt att följa tidigare vägledning kring privat nätverkskoppling för att undvika överbelastning över gränserna. Teams realtidsmediatrafik utnyttjar den konfigurationen som förut.
2.  Implementera ett delat/hybridmönster. 

  - Använd föregående vägledning för all trafik som flaggats för optimering utom Teams-möten och samtal med mediatrafik i realtid.

  - Dirigera Teams-möten och ringa mediatrafik i realtid via det offentliga internet. I följande information finns information om hur du identifierar realtidsmedianätverkstrafik.

Att skicka teams ljud- och videotrafik i realtid via det offentliga Internet, som använder anslutningen med högre kvalitet, kan leda till betydande kostnadsbesparingar, eftersom det är gratis jämfört med att betala för att skicka den trafiken via ett privat nätverk. Det kan finnas liknande ytterligare fördelar om användarna även använder SDWAN- eller VPN-klienter. Vissa organisationer kanske också föredrar att ha mer av sina data passerar allmänna Internetanslutningar som en allmän övning.

Samma alternativ kan gälla för SDWAN- eller VPN-konfigurationer. En användare använder till exempel en SDWAN eller VPN för att dirigera Microsoft 365-trafik till företagsnätverket och sedan utnyttjar den privata utökningen av nätverket för att undvika överbelastning över kantlinjer. Användarens SDWAN eller VPN kan nu konfigureras för att utesluta Teams-möte och ringa realtidstrafik från VPN-routningen. Den här VPN-konfigurationen kallas för delade tunnlar. Mer information [finns i VPN-delade tunnlar för Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)

Du kan också fortsätta att använda din SDWAN eller VPN för all Microsoft 365-trafik, inklusive för realtidstrafik i Microsoft Teams. Microsoft har inga rekommendationer om användningen av SDWAN- eller VPN-lösningar.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Metodtips för hem-, mobil- och användarnätverkstips för Teams-möten

Användare i Kina kan dra nytta av förbättringarna genom att helt enkelt ansluta till den offentliga Internettjänsten i Kina med en fast telefon eller mobil anslutning. Teams realtidsmedia för ljud- och videotrafik på det offentliga internet direkt dra nytta av förbättrad anslutning och kvalitet.

Men data från andra Microsoft 365-tjänster – och annan trafik i Teams, till exempel chatt eller filer – kommer inte direkt att dra nytta av dessa förbättringar. Användare utanför organisationen kan fortfarande uppleva dålig nätverksprestanda för den här trafiken. Som beskrivs i den här artikeln kan du minimera dessa effekter med hjälp av en VPN eller SDWAN. Du kan också se till att användarna använder avancerade skrivbordsklienter över webbklienter, som har stöd för cachelagring i programmet för att minimera nätverksproblem.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identifiera Teams realtidsmedianätverkstrafik

För att konfigurera en nätverksenhet eller en VPN/SDWAN-konfiguration måste du utesluta endast Teams realtidsmedia för ljud- och videotrafik. Trafikinformationen finns för ID 11 i den officiella listan över [Office 365 URL:er och IP-adressintervall.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Alla andra nätverkskonfigurationer ska förbli som de är.

Microsoft arbetar kontinuerligt med att förbättra användarupplevelsen och prestandan för klienter i hela intervallet av nätverksarkitekturer och egenskaper. Besök [Office 365 Networking Tech Community]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) för att starta eller delta i en konversation, hitta resurser och skicka funktionsförfrågningar och förslag

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksplanering och prestandajustering för Microsoft 365](./network-planning-and-performance.md)

[Microsoft 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Microsofts globala nätverk](/azure/networking/microsoft-global-network)